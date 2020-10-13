<template>
<div class = "Messages" id = 'scroll'>
  <ul id="v-for-object" class="demo">
  <li v-for="(msg,i) in messages" :key="i">
    <div v-if="msg.name != user" class = "MsgName1">
      <b>{{msg.name}}</b><br>
      <div class = "ra">{{msg.text}}</div>
      </div>
    <div v-else class = "MsgName2">
      <b>{{msg.name}}</b><br>
      <div class = "ra">{{msg.text}}:</div>
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
.MsgName1{
  margin-top:10px;
  font-size: 20px;
  color:#0d4bd6;
  word-wrap: break-word;
  width:200px;
  border: 1px solid #5580a3;
  border-radius: 10%;
}
.MsgName2{
  margin-top:10px;
  font-size: 20px;
  color:#0b8fc1;
  margin-left: 260px;
  word-wrap: break-word;
  border: 1px solid #5580a3;
  border-radius: 10%;
  width:250px;
}
li{
    margin-top:10px;
    list-style-type: none;
}
.ra{
  margin-left: 20px;
}
</style>
