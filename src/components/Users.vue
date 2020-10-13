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
    .usersList{
      float:left;
        width:300px;
        height:500px;
        overflow-y: scroll;
        background-color: #ffc33c;
        text-align: center;
        font-size: 30px;
    }
    .user{
      color:#926006;
    }
    .d{
      color:white;
    }
    .s{
      color: #002a3e;
    }
</style>
