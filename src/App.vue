<template>
  <div class="home">
    <HelloWorld v-if="showSomething" @clickBTN="click" :users = "UsersList" :root = "root"/>
    <Users :name = "user" :users = "UsersList" v-if="showUserList"/>
    <Messages v-chat-scroll :messages = "MessagesList" :user = "user" v-if="showMessages" :time = "Time"/>
    <Exit v-if="showExit" @Exit="ChatExit"/>
    <MessageForm :root = "root" :user = "user" v-if="showMsgForm"/>
    <!-- v-show="REG" -->
  </div>
</template>

<script>
import randomstring from 'randomstring'
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Users from '@/components/Users.vue'
import MessageForm from '@/components/MessageForm.vue'
import Messages from '@/components/Messages.vue'
import Exit from '@/components/ChatExit.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld,
    Users,
    MessageForm,
    Messages,
    Exit
  },
  data: function () {
    return {
      showSomething: true,
      showUserList: false,
      showMessages: false,
      showMsgForm: false,
      showExit: false,
      root: 'http://localhost:3000/', // api.stepchat.site
      user: '',
      message: '',
      MessagesList: null,
      UsersList: [0],
      Time: {},
      avatarList: null
    }
  },
  computed: {
    totalUsers () {
      return this.UsersList.length
    },
    users () {
      return this.UsersList.map((user) => {
        return {
          name: user,
          avatar: `https://robohash.org/${randomstring.generate(7)}`
        }
      })
    }
  },
  watch: {
    totalUsers: function (newVal, oldVal) {
      console.log(newVal)
    }
  },
  methods: {
    click (a) {
      this.showSomething = false
      this.showUserList = true
      this.showMessages = true
      this.showMsgForm = true
      this.showExit = true
      this.user = a
    },
    ChatExit () {
      console.log('exit')
      fetch(`http://localhost:3000/user/${this.user}`, {
        method: 'DELETE',
        headers: {
          'Content-Type': 'application/json;charset=utf-8'
        }
      })
      location.reload()
    }
  },
  async beforeMount () {
    setInterval(async () => {
      const response = await fetch(this.root)
      if (response.ok) {
        var now = new Date()
        const TimeChange = now.getHours() - now.getUTCHours()
        const data = await response.json()
        this.MessagesList = data.messages
        this.UsersList = data.users
        this.Time = data.time
        let counter = 0
        this.Time.hour.forEach(element => {
          this.Time.hour[counter] = this.Time.hour[counter] + TimeChange
          counter++
        })
      }
    }, 1000)
  }
}
</script>

<style>
body{
  background-color: #5580a3;
}
</style>
