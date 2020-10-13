<template>
<div class = "usersList">
    <div class = "user" v-for="(user, i) in users" :key="i">
        <div v-if="name==user" class = "s">
          <b>{{user}}</b>
        </div>
        <div v-else class = "d">
          {{user}}
        </div>
      </div>
</div>

</template>

<script>

export default {
  name: 'users',
  props: {
    users: Array,
    name: String
  }
}
</script>

<style>
::-webkit-scrollbar { width: 5px; height: 3px;}
::-webkit-scrollbar-track-piece { background-color: #ffffff;}
::-webkit-scrollbar-thumb { height: 50px; background-color:#7d92f9;}
    .usersList{
      float:left;
        width:300px;
        height:500px;
        overflow-y: scroll;
        background-color: #1f3b6d;
        text-align: center;
        font-size: 30px;
        scrollbar-3dlight-color: blueviolet;
    }
    .user{
      color:#926006;
    }
    .d{
      color:white;
    }
    .s{
      color: #5da6ff;
    }
</style>
