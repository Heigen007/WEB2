<template>
<div class = "reg" v-on:keyup.enter="submit">
  <div class = "text">Регистрация</div>
  <input type="text" id = 's' class = "input" autocomplete="off" placeholder="Логин:">
  <div class = "c"><button class = "but"  @click="click">Войти в чат</button></div>
  <div class="mistake" v-if="showmi">Введите логин!</div>
  <div class="mistake" v-if="showmiHei">Имя занято!</div>
</div>

</template>

<script>

export default {
  name: 'HelloWorld',
  props: {
    users: Array,
    root: String
  },
  data: function () {
    return {
      showmi: false,
      er: false,
      showmiHei: false,
      NameCorrect: true
    }
  },
  methods: {
    click () {
      this.NameCorrect = true
      const dar = document.getElementById('s')
      if (dar.value) {
        this.users.forEach(element => {
          if (element === dar.value) {
            this.NameCorrect = false
          }
        })
      }
      if (this.NameCorrect === false) {
        this.showmiHei = true
        this.showmi = false
      } else if (dar.value) {
        const user = {
          name: dar.value
        }
        dar.value = ''
        fetch(`${this.root}user`, {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json;charset=utf-8'
          },
          body: JSON.stringify(user)
        })
        this.$emit('clickBTN', user.name)
        this.showmi = false
      } else {
        this.showmi = true
        this.showmiHei = false
      }
    },
    submit () {
      this.click()
    }
  }
}
</script>

<style scoped lang="scss">
.input{
    border: 5px solid blue;
    width: 200px;
    height:50px;
    font-size: 40px;
    margin-top: 2%;
    border-radius: 10%;
    color: #483916;
    outline: none;
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
    outline: none;
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
.mistake{
  font-size: 30px;
  padding:10px;
  margin-left: 10px;
  color:#b11000;
}
</style>
