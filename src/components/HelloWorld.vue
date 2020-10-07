<template>
<div class = "reg">
  <div class = "text">Регистрация</div>
  <input type="text" id = 's' class = "input">
  <div><button class = "but" @click="click">Войти в чат</button></div>
</div>

</template>

<script>

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  methods: {
    click () {
      console.log('d')
      const dar = document.getElementById('s')

      const user = {
        name: dar.value
      }
      fetch('http://localhost:3000/user', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json;charset=utf-8'
        },
        body: JSON.stringify(user)
      })
    }
  }
}

</script>

<style scoped lang="scss">
.input{
    border: 5px solid blue;
    width: 200px;
    height:50px;
    font-size: 50px;
    margin-top: 2%;
    border-radius: 10%;
}
.text{
  font-size: 100px;
  color: #e28a61;
}
.but{
    font-size: 50px;
    margin-top: 3%;
}

</style>
