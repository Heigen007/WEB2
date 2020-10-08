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
    color:#41cccc;
    height: 45px;
    width: 500px;
    float:left;
    font-size: 20px;
}
.MsgBut{
  height:45px;
  width:100px;
}
</style>
