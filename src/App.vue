<template>
  <div class="menu">
    <a v-for="menu in menuList" :key="menu">{{ menu }}</a>    
  </div>

  <!-- 모달창 -->

  <div v-if="roomDetail.isModal" class="black-bg" @click="closeRoomDetail()">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>{{ products[roomDetail.choiceRoom].detail }}</p>
      <button @click="closeRoomDetail()">닫기</button>
    </div>
  </div>


  <div v-for="(product,index) in products" :key="product.name">

    <img :src="require(`@/assets/${product.roomImg}`)" class="room-img"/>
  
    <h4 @click="showRoomDetail(index)">{{product.name}}</h4>
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
      roomDetail : {
        isModal :false,
        choiceRoom : null,
      },
      products : [
        { name : '역삼동 원룸', price : 80, declaration: 0, roomImg:"room0.jpg",  detail : "상세페이지 내용1"},
        { name : '천호동 원룸', price : 50, declaration: 0, roomImg:"room1.jpg",  detail : "상세페이지 내용2"},
        { name : '마포구 원룸', price : 70, declaration: 0, roomImg:"room2.jpg",  detail : "상세페이지 내용3"},
      ]    
    }
  },
  methods : {
    addDeclaration(index){
      this.products[index].declaration += 1;
    }, 
    showRoomDetail(index){
      this.roomDetail.choiceRoom = index;
      this.roomDetail.isModal = true;
    },
    closeRoomDetail(){
      this.roomDetail.isModal = false;
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

