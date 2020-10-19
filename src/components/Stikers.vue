<template>
<div class = "Stikers">
    <img src="../assets\svg\001-monitor.svg" class = "Stiker">
    <img src="../assets\svg\002-smile-1.svg" class = "Stiker">
    <img src="../assets\svg\003-diamond.svg" class = "Stiker">
    <img src="../assets\svg\004-bar-chart.svg" class = "Stiker">
    <img src="../assets\svg\168-padlock.svg" class = "Stiker">
    <img src="../assets\svg\159-email.svg" class = "Stiker">
    <img src="../assets\svg\160-chat.svg" class = "Stiker">
    <img src="../assets\svg\166-hourglass.svg" class = "Stiker">
    <img src="../assets\svg\147-medal.svg" class = "Stiker">
</div>

</template>

<script>

export default {
  name: 'Stickers'
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
