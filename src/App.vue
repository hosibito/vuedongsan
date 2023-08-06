<template>
  <div class="menu">
    <a v-for="menu in menuList" :key="menu">{{ menu }}</a>    
  </div>

  <div v-for="(product,index) in products" :key="product.name">
    <h4>{{product.name}}</h4>
    <p>{{product.price}}만원</p>
    <button @click="addDeclaration(index)">허위매물신고</button>
    <span>신고수 : {{product.declaration}}</span>
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
      products : [
        { name : '역삼동 원룸', price : 80, declaration: 0},
        { name : '천호동 원룸', price : 50, declaration: 0},
        { name : '마포구 원룸', price : 70, declaration: 0},
      ]    
    }
  },
  methods : {
    addDeclaration(index){
      this.products[index].declaration += 1;
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

