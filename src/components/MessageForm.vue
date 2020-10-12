<template>
<div class = "MessageForm" v-on:keyup.enter="send">
   <input id = "input" class = "MsgText" placeholder="Введите сообщение:">
   <img src="../assets\Sen.svg" class = "MsgBut"  @click="click">
</div>

</template>

<script>

export default {
  name: 'MessageForm',
  props: {
    user: String,
    root: String
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
        fetch(`${this.root}message`, {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json;charset=utf-8'
          },
          body: JSON.stringify(text)
        })
      }
      dar.value = ''
    },
    send () {
      this.click()
    }
  }
}
</script>

<style scoped lang="scss">
.MsgText{
    color:#41cccc;
    height: 48px;
    width: 550px;
    float:left;
    font-size: 20px;
    outline: none;
    border:none;
}
.MsgText:focus{
      height: 45px;
  border-bottom: 3px solid #47a3f3;
}
.MsgBut{
  height:50px;
  width:50px;
}
</style>
