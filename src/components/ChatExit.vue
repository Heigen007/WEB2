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
        width:290px;
        height:40px;
        padding: 5px;
        background-color: #002a3e;
        color:white;
        text-align: center;
        font-size: 30px;
        cursor: pointer;
    }

</style>
