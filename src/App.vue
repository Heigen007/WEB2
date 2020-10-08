<template>
  <div class="home">
    <HelloWorld v-if="showSomething" @clickBTN="click"/>
    <Users :users = "UsersList" v-if="showUserList"/>
    <Messages :messages = "MessagesList" v-if="showMessages"/>
    <MessageForm v-if="showMsgForm"/>
    <!-- v-show="REG" -->
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Users from '@/components/Users.vue'
import MessageForm from '@/components/MessageForm.vue'
import Messages from '@/components/Messages.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld,
    Users,
    MessageForm,
    Messages
  },
  data: function () {
    return {
      showSomething: true,
      showUserList: false,
      showMessages: false,
      showMsgForm: false,
      root: 'http://localhost:3000/',
      user: '',
      message: '',
      MessagesList: null,
      UsersList: null
    }
  },
  methods: {
    click () {
      this.showSomething = false
      this.showUserList = true
      this.showMessages = true
      this.showMsgForm = true
    }
  },
  async beforeMount () {
    setInterval(async () => {
      console.log('a')
      const response = await fetch(this.root)
      if (response.ok) {
        const data = await response.json()
        this.MessagesList = data.messages
        this.UsersList = data.users
        console.log('2')
        console.log(data.users)
        console.log(data.messages)
      }
    }, 1000)
  }
}
</script>

<style>
body{
  background-color: #2e93f9;
}
</style>
