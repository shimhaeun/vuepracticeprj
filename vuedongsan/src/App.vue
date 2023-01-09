<template>

  <div class="menu">
    <a v-for="a in menus" :key="a">{{a}}</a>
  </div>
  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="모달창열렸니 = false">close</button>
  </div>
  </div>

  <div>
  
    <h4>{{a}}</h4>
    <p @click="모달창열렸니 = true">50만원</p>
    <button @click="increase">허위매물신고</button> <span>신고 수 : {{ 신고수 }}</span>
  </div>
  <img src="./assets/지리산하은2.jpeg" class="room-img">
  
</template>

<script>



export default {
  name: 'App',
  data(){
    return {
      모달창열렸니 : false,
      신고수 : 0,
      menus : ['HOME', 'SHOP', 'ABOUT'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
    }
  },
  methods : { // 함수 만드는 공간
    increase(){
      this.신고수++;
    },

  },
  components: {
  }
}
</script>

<style>
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height: 100%;
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
  margin-top: 40px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
</style>
