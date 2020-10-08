<template>
<div class = "Messages">
  <ul id="v-for-object" class="demo">
  <li v-for="(msg,i) in messages" :key="i">
    <div class = "MsgName">{{msg.name}}:</div>
    <div class = "MsgText">{{msg.text}}</div>
    </li>
</ul>
</div>

</template>

<script>

export default {
  name: 'Messages',
  props: {
    messages: Array
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
}
li{
    margin-top:10px;
    list-style-type: none;
}
</style>
