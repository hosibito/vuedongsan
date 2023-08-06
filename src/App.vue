<template>
  <div class="menu">
    <a v-for="menu in menuList" :key="menu">{{ menu }}</a>    
  </div>

  <div class="menu">
    <a v-for="(menu, index) in menuList" :key="index">{{ menu }} / {{ index }}</a>    
  </div>

  <div v-for="product in products" :key="product">
    <h4>{{ product }}</h4>
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
      menuList : ['Home', 'Products', 'About'],
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

}

.menu {
  background : darkslateblue;
  padding : 15px;
  border-radius : 5px;
}
.menu a {
  color : white;
  padding : 10px;
}
</style>
