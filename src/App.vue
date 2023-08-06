<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div>
    <h4 :style="styleH4">{{ products[0] }}</h4>
    <p>{{ price1 }} 만원</p>
  </div>
  <div>
    <h4>{{ products[1] }}</h4>
    <p>XX 만원</p>
  </div>
</template>

<script>


export default {
  name: 'App',
  components: {

  },
  data(){
    return{
      price1 :60,
      styleH4 : 'color: red',
      products : ['역삼동 원룸', '천호동 원룸', '마포구 원룸']
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
