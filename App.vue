<template>  

  <div class="black-bg" v-if= "모달창Open == true" >
    <div class="white-bg">
      <h4>상새페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click = "모달창Open == false">닫기</button>
    </div>
  </div>


  <!-- 상단 매뉴  -->
  <div class = "menu">
    <a v-for= "a in 메뉴들" :key="a">{{a}}</a>
  </div>
  <img alt="Vue logo" src="./assets/logo.png">


  <h2 v-for= "o in 원룸" :key="o">{{o}}</h2>
  <h2 class = "blue" :style= "styleB">원룸샵</h2>
 
  <div>    
    <img :src="원룸들[0].image" class="room-img"> 
    <!-- 긁어온 상대경로 src\assets\Room1.jpg -->
    <h3>{{ 원룸들[0].title }}</h3>
    <h4>{{ 원룸들[0].price }}</h4>
    <h1></h1>
  </div>  <div>    
    <img :src="원룸들[1].image" class="room-img"> 
    <!-- 긁어온 상대경로 src\assets\Room1.jpg -->
    <h3>{{ 원룸들[1].title }}</h3>
    <h4>{{ 원룸들[1].price }}</h4>
    <h1></h1>
  </div>  <div>    
    <img :src="원룸들[2].image" class="room-img"> 
    <!-- 긁어온 상대경로 src\assets\Room1.jpg -->
    <h3>{{ 원룸들[2].title }}</h3>
    <h4>{{ 원룸들[2].price }}</h4>
    <h1></h1>
  </div>
</template>

<script>

import roomsData from './assets/oneRoom.js';

export default {
  name: 'App',  
  data(){
    return {
      원룸들: roomsData, 
      모달창Open : false,
      // 모달창의 상태를 적은 부분을 state라고 부름
        메뉴들 : ['Home', 'Shop', 'About'],
        styleB : 'color : blue',
        
        prodect : ['역삼동원룸', '천호도원룸', '마포구원룸']
    }
  },

  components: {
  }
}
</script>

<style>
body{
  margin: 0
}
div{
  box-sizing: border-box;
}
.black-bg{
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed; 
  padding: 20px;
}
.white-bg{
  width:20%; background:  white;
  border-radius: 8px;
  padding: 20px;
}

.room-img{
  width: 50%;
  margin-top: 40px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

/* 상단 매뉴 */
.menu {
  background : darkslateblue;
  padding :15px;
  border-radius: 5px;
}
.menu a{
  color: white;
  padding: 10px;
}
</style>