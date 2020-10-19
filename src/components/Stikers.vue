<template>
<div class = "Stikers">
    <img src="../assets\svg\1.svg" class = "Stiker" @click="click(1)">
    <img src="../assets\svg\2.svg" class = "Stiker" @click="click(2)">
    <img src="../assets\svg\3.svg" class = "Stiker" @click="click(3)">
    <img src="../assets\svg\4.svg" class = "Stiker" @click="click(4)">
    <img src="../assets\svg\5.svg" class = "Stiker" @click="click(5)">
    <img src="../assets\svg\6.svg" class = "Stiker" @click="click(6)">
    <img src="../assets\svg\7.svg" class = "Stiker" @click="click(7)">
    <img src="../assets\svg\8.svg" class = "Stiker" @click="click(8)">
    <img src="../assets\svg\9.svg" class = "Stiker" @click="click(9)">
</div>

</template>

<script>

export default {
  name: 'Stickers',
  methods: {
    click (i) {
      console.log(i)
    }
  }
}
</script>

<style lang="scss">
.Stikers{
  display: grid;
  grid-template-columns: 50px 50px 50px;
  grid-template-rows: 50px 50px 50px;
}
.Stiker{
  width: 30px;
}
</style>
