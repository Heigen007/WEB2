<template>
<div class = "MessageForm">
   <input class = "MsgText" placeholder="Введите сообщение:">
   <img src="Sen.svg" class = "MsgBut">
</div>

</template>

<script>

export default {
  name: 'MessageForm',
  props: {
    msg: String
  }
}

</script>

<style scoped lang="scss">
.MsgText{
    color:red;
    height: 45px;
    width: 500px;
    // float:left;
}
.MsgBut{
  height:45px;
  width:100px;
}
</style>
