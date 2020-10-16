<template>
<div class = "usersList">
    <div class = "user" v-for="(user, i) in users" :key="i">
        <div class="avatar">
        <img :src="user.avatar" />
      </div>
        <div v-if="name==user.name" class = "s">
          <b>{{user.name}}</b>
        </div>
        <div v-else class = "d">
          {{user.name}}
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

<style lang="scss">
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
   display: flex;
   flex-direction: row;
   flex-wrap: nowrap;
   align-items: center;
   margin-bottom: 2px;
      .d{
        color:white;
      }
      .s{
        color: #5da6ff;
      }
      .avatar {
      box-sizing: border-box;
      border: 2px solid #53A2BD;
      border-radius: 50%;
      overflow: hidden;
      margin-right: 2px;
      width: 70px;
      }
      .avatar img{
        width: 60px;
      }
    }
</style>
