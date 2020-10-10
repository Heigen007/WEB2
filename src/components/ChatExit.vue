<template>
<div class = "ChatExit" @click="click">Выйти</div>
</template>

<script>

export default {
  name: 'Exit',
  methods: {
    click () {
      this.$emit('Exit')
    }
  }

}
</script>

<style>
    .ChatExit{
      float:left;
        width:300px;
        height:50px;
        background-color: #d37204;
        text-align: center;
        font-size: 30px;
    }

</style>
