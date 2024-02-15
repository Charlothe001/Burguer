<script>
import { RouterLink, RouterView } from 'vue-router';
import NavBar from './components/NavBar.vue';
import Footer from './components/Footer.vue';

export default{
  components:{
    NavBar,
    Footer
  },
  data(){
    return {
      logo_src:"/img/logo.png",
      app_name:"Burgueria do Pai"
    }
  }
}

</script>

<template>
  <NavBar :logo="logo_src" :alt="app_name"/>
  <RouterView />
  <Footer/>
</template>

<style>
*{
  font-family: Helvetica;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

.main_container{
  margin: 50px;
  min-height: 485px;
}

h1{
  text-align: center;
  font-size: 42px;
  margin-bottom: 30px;
  color: #222;
}

.main_card{
display: flex;
flex-direction: column;
}

.main_card h2{
  margin-bottom: 20px;
}
</style>
