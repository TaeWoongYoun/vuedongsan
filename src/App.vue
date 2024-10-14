<template>
  <div id="app">
    <nav>
      <a href="#" v-for="(a,i) in menu" :key="i">{{ a }}</a>
    </nav>
    <div v-for="(p,i) in products" :key="i">
      <h4>{{ p }}</h4>
      <p>{{ price[i] }} 만원</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return{
      menu :['Home', 'Shop', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      price : ['50', '60', '70'],
    }
  },
  components: {
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

nav{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

nav a{
  color: #fff;
  text-decoration: none;
  padding: 10px;
}
</style>
