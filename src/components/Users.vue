<template>
<div class = "usersList">
    <div v-for="(user, i) in users" :key="i">{{user}}</div>
</div>

</template>

<script>

export default {
  name: 'users',
  props: {
    users: Array
  }
}
</script>

<style>
    .usersList{
        width:300px;
        height:500px;
        overflow: scroll;
        background-color: red;
    }
</style>
