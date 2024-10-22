<template>
    <header>
        <div class="logo">
            <h1>Vuedongsan</h1>
        </div>
        <nav>
            <a href="#" v-for="(a,i) in menu" :key="i">{{ a }}</a>
        </nav>
    </header>
</template>

<script>
export default {
    data(){
        return{
            menu :['Home', 'Shop', 'About']
        }
    },
}
</script>

<style scoped>
header{
    background: darkblue;
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
</style>