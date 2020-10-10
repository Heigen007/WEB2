<template>
<div class = "Messages" id = 'scroll'>
  <ul id="v-for-object" class="demo">
  <li v-for="(msg,i) in messages" :key="i">
    <div v-if="msg.name != user" class = "MsgName">{{msg.name}}:</div>
    <div v-else class = "MsgName2">
      {{msg.name}}:
    </div>
    <div v-if="msg.name != user"  class = "MsgText">{{msg.text}}</div>
    <div v-else class = "MsgText2">
      {{msg.text}}
    </div>
    </li>
</ul>
</div>

</template>

<script>

export default {
  name: 'Messages',
  props: {
    messages: Array,
    user: String
  }
}

</script>

<style scoped lang="scss">
.Messages{
    width:600px;
    height:450px;
    overflow-y: scroll;
    background-color: #ffaf76;
    font-size: 30px;
    color:#3489d2;
}
.MsgName{
  margin-top:10px;
  font-size: 20px;
  color:#bf1a1a;
  margin-left: -40px;
}
.MsgText{
    margin-top:5px;
     word-wrap: break-word;
     width:240px;
}
.MsgName2{
  margin-top:10px;
  font-size: 20px;
  color:#bf1a1a;
  margin-left: 260px;
}
.MsgText2{
    margin-top:5px;
    margin-left: 300px;
     word-wrap: break-word;
     width:240px;
}
li{
    margin-top:10px;
    list-style-type: none;
}
</style>
