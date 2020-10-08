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
      if (dar.value) {
        const user = {
          name: dar.value
        }
        dar.value = ''
        fetch('http://localhost:3000/user', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json;charset=utf-8'
          },
          body: JSON.stringify(user)
        })
        this.$emit('clickBTN')
      }
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
    color: #483916;
}
.input:hover{
  border-color: #246eb7;
}
.text{
  font-size: 100px;
  color: #e28a61;
}
.but{
    font-size: 50px;
    margin-top: 3%;
    background-color: #ffa377;
}
.but:hover{
      background-color: #ffc6ab;
}
.reg{
  display:flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
</style>
