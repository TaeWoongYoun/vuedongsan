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

    <div class="black-bg" v-if="modal !== null">
      <div class="white-bg">
        <h2>상세페이지</h2>
        <p>{{ data[modal].content }}</p>
        <button @click="closeModal">닫기</button>
      </div>
    </div>

    <div class="grid-box">
      <div v-for="(p,i) in data" :key="i" class="room-box">
        <img :src="p.image" alt="" class="room-img">
        <h5 @click="openModal(i)" class="title">{{ p.title }}</h5>
        <p class="price">가격 : {{ p.price }}원</p>
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
      modal : null,
      menu :['Home', 'Shop', 'About']
    }
  },
  methods: {
    openModal(index) {
      this.modal = index;
    },
    closeModal() {
      this.modal = null;
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
  height: 250px;
  margin: 20px 10px;
  background-color: #eee;
  border-radius: 20px;
  overflow: hidden;
  padding: 10px;
}

.room-box > .room-img{
  width: 100%;
  height: 150px;
  border-radius: 15px;
}
</style>