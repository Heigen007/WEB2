<template>
<div class = "MessageForm" v-on:keyup.enter="send">
   <input id = "input" class = "MsgText" placeholder="Введите сообщение:">
   <img :src="require(`../assets/Sen.svg`)" class = "MsgBut"  @click="click">
   <div id = "Touch" class = "down" >
     <img src="../assets\down.svg" class = "DownBut" @click="Downclick">
     <Stikers v-if="Hi" class = "stik"/>
   </div>
</div>

</template>

<script>

import Stikers from '@/components/Stikers.vue'

export default {
  name: 'MessageForm',
  components: {
    Stikers
  },
  data: function () {
    return {
      Hi: false
    }
  },
  props: {
    user: String,
    root: String
  },
  methods: {
    // json-formatter
    click () {
      const dar = document.getElementById('input')
      if (dar.value) {
        var now = new Date()
        var date = new Date(2014, 11, 31, now.getUTCHours(), now.getUTCMinutes(), now.getUTCSeconds())
        var options = {
          minute: 'numeric',
          second: 'numeric'
        }
        const text = {
          name: this.user,
          text: dar.value,
          time: {
            hour: now.getUTCHours(),
            minut: date.toLocaleString('ru', options)
          }
        }
        fetch(`${this.root}message`, {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json;charset=utf-8'
          },
          body: JSON.stringify(text)
        })
      }
      dar.value = ''
    },
    send () {
      this.click()
    },
    Downclick () {
      const h = document.getElementById('Touch')
      if (h.style.height === '240px') {
        h.style.height = '20px'
        this.Hi = false
      } else {
        h.style.height = '240px'
        this.Hi = true
      }
    }
  }
}
</script>

<style scoped lang="scss">
.MsgText{
    color:#41cccc;
    height: 50px;
    width: 550px;
    float:left;
    font-size: 20px;
    outline: none;
    border:none;
    padding: 0;
}
.MsgText:focus{
      height: 47px;
  border-bottom: 3px solid #47a3f3;
}
.MsgBut{
  width:50px;
}
.down{
  margin-top: -4px;
  text-align:center;
  width: 550px;
  margin-left: 300px;
  height: 20px;
  background-color: #a1d1ec;
  // transition: height 1s;
  align-items: center;
}
img{
  width: 15px;
}
.stik{
  margin-left: 210px;
}
</style>
