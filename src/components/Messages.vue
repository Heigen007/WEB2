<template>
<div class = "Messages" id = 'scroll'>
  <ul id="v-for-object" class="demo">
  <li v-for="(msg,i) in messages" :key="i">
    <div v-if="msg.name != user" class = "MsgName1">
      <b>{{msg.name}}:</b><br>
      <div class = "ra">{{msg.text}}</div>
      <div class = "time">{{time.hour[i]}}:{{time.minut[i]}}</div>
      </div>
    <div v-else class = "MsgName2">
      <b>{{msg.name}}:</b><br>
      <div class = "ra">{{msg.text}}</div>
      <div class = "time">{{time.hour[i]}}:{{time.minut[i]}}</div>
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
    user: String,
    time: Object
  }
}

</script>

<style scoped lang="scss">
::-webkit-scrollbar { width: 5px; height: 3px;}
::-webkit-scrollbar-track-piece { background-color: #ffffff;}
::-webkit-scrollbar-thumb { height: 50px; background-color:#7d92f9;}
.Messages{
    width:600px;
    height:500px;
    overflow-y: scroll;
    background-color: #0d2c3e;
    font-size: 30px;
    color:#fff;
}
.MsgName1{
  margin-top:10px;
  font-size: 20px;
  word-wrap: break-word;
  width:250px;
  border: 1px solid #8095ff;
  border-radius: 10%;
  margin-left: -5px;
}
.MsgName2{
  margin-top:10px;
  font-size: 20px;
  margin-left: 265px;
  word-wrap: break-word;
  border: 1px solid #8095ff;
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
.time{
  margin-left: 210px;
  font-size: 15px;
}
</style>
