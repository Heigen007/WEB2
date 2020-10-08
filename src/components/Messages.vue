<template>
<div class = "Messages">
    <div class = "Msgname" v-for="(msg, i) in messages" :key="i">{{msg.name}}</div>
    <div class = "Msgtext" v-for="(msg, i) in messages" :key="i">{{msg.text}}</div>
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
    text-align: center;
    font-size: 30px;
    color:#3489d2;
}
.Msgname{
  margin-top:10px;
  font-size: 20px;
  color:#bf1a1a;
}
.Msgtext{
    margin-top:5px;
}
</style>
