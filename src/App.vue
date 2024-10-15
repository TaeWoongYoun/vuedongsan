<template>
  <div id="app">
    <header>
      <div class="logo">
        <h1>Vuedongsan</h1>
      </div>
      <nav>
        <a href="#" v-for="(a,i) in menu" :key="i">{{ a }}</a>
      </nav>
    </header>

    <div class="black-bg" v-if="modal == true">
      <div class="white-bg">
        <h2>상세페이지</h2>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Rem expedita officia consequuntur voluptate dignissimos architecto dolores eaque minus, cupiditate asperiores unde reprehenderit quisquam ut incidunt dicta dolore odio quidem? Magnam.</p>
        <button @click="modal = false">닫기</button>
      </div>
    </div>

    <div class="grid-box">
      <div v-for="(p,i) in data" :key="i" class="room-box">
        <img :src="data[i].image" alt="" class="room-img">
        <h5 @click="modal = true" class="title">{{ data[i].title }}</h5>
        <p class="price">가격 : {{ data[i].price }}원</p>
        <p class="declaration"><button @click="increase(i)">허위매물신고</button> <span>신고수 : {{num[i]}}</span></p>
      </div>
    </div>
  </div>
</template>

<script>
import data from './data/post.js'

export default {
  name: 'App',
  data(){
    return{
      data : data,
      modal : false,
      num : [0,0,0,0,0,0,0,0,0,0,0],
      menu :['Home', 'Shop', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸','남동구원룸','부평구원룸','논현동원룸','미추홀구원룸','노원구원룸','송도원룸','만수동원룸','그냥원룸'],
      price : ['50', '60', '70','80','55','75','100','50','88','90','0.1'],
    }
  },
  methods: {
    increase(index) {
      this.num[index]++;
    }
  },
  components: {
  }
}
</script>

<style>
body{
  margin: 0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

header{
  background: darkslateblue;
  color: #fff;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo{
  width: 300px;
}

nav{
  width: 300px;
}

nav a{
  color: #fff;
  text-decoration: none;
  padding: 10px;
}

.black-bg{
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  top: 0;
  padding: 20px;
}

.white-bg{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 500px;
  background: #fff;
  border-radius: 10px;
  padding: 20px;
}

.grid-box{
  margin-top: 50px;
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
}

.room-box{
  width: 300px;
  height: 300px;
  margin: 20px 10px;
  background-color: #eee;
  border-radius: 20px;
  overflow: hidden;
}

.room-box > .room-img{
  width: 100%;
  height: 150px;
}
</style>