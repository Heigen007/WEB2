<template>
<div class = "MessageForm">
   <input id = "input" class = "MsgText" placeholder="Введите сообщение:">
   <img src="../assets\Sen.svg" class = "MsgBut"  @click="click">
</div>

</template>

<script>

export default {
  name: 'MessageForm',
  props: {
    user: String
  },
  methods: {
    // json-formatter
    click () {
      const dar = document.getElementById('input')
      if (dar.value) {
        const text = {
          name: this.user,
          text: dar.value
        }
        fetch('http://localhost:3000/message', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json;charset=utf-8'
          },
          body: JSON.stringify(text)
        })
        console.log('lllllllllllllll')
      }
    }
  }
}
</script>

<style scoped lang="scss">
.MsgText{
    color:#41cccc;
    height: 45px;
    width: 550px;
    float:left;
    font-size: 20px;
}
.MsgBut{
  height:50px;
  width:50px;
}
</style>
