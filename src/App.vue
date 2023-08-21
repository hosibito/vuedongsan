<template>
  <div class="menu">
    <a v-for="menu in menuList" :key="menu">{{ menu }}</a>    
  </div>

  <!-- 모달창 -->
  <div v-for = "(product) in products" :key="product.name">
    <div v-if="product.isDetail" class="black-bg" @click="product.isDetail=false">
      <div class="white-bg">
        <h4>상세페이지</h4>
        <p>{{product.detail}}</p>
        <button @click="product.isDetail=false">닫기</button>
      </div>
    </div>
  </div>

  <div v-for="(product,index) in products" :key="product.name">

    <img :src="require(`@/assets/${product.roomImg}`)" class="room-img"/>
  
    <h4 @click="product.isDetail=true">{{product.name}}</h4>
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
        { name : '역삼동 원룸', price : 80, declaration: 0, roomImg:"room0.jpg", isDetail : false, detail : "상세페이지 내용1"},
        { name : '천호동 원룸', price : 50, declaration: 0, roomImg:"room1.jpg", isDetail : false, detail : "상세페이지 내용2"},
        { name : '마포구 원룸', price : 70, declaration: 0, roomImg:"room2.jpg", isDetail : false, detail : "상세페이지 내용3"},
      ]    
    }
  },
  methods : {
    addDeclaration(index){
      this.products[index].declaration += 1;
    }, 
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



body {
  margin : 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height:100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
} 



.room-img {
  width: 100%;
  margin-top:40px

}
</style>

