<template>
  <div class="home">
    <HelloWorld v-if="showSomething" @clickBTN="click"/>
    <Users />
    <MessageForm />
    <Messages :messages = "MessagesList" />
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
      root: 'http://localhost:3000/',
      user: '',
      message: '',
      MessagesList: null,
      usersList: null
    }
  },
  methods: {
    click () {
      this.showSomething = false
    }
  },
  async beforeMount () {
    setInterval(async () => {
      console.log('a')
      const response = await fetch(this.root)
      if (response.ok) {
        const data = await response.json()
        this.MessagesList = data.Messages
        this.usersList = data.users
      }
    }, 1000)
  }
}
</script>

<style>
body{
  background-color: #00366d;
}
</style>
