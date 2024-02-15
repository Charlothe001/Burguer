<script>
  import Banner from '../components/Banner.vue';
  import BurguerCard from '../components/BurguerCard.vue';

  export default{
    name: "Home",
    components: {
      Banner,
      BurguerCard,      
    }
  }
</script>

<template>
  <Banner/>
  <div class="main_container">
    <h1>Menu:</h1>
    <BurguerCard/>
  </div>
</template>

<style >
  #main_banner{
    background-image: url('/img/burger.jpg');
    background-position: 0 -250px;
    background-size: cover;
    height: 500px;
    display: flex;
    align-items: center;
    justify-content: flex-start;
  }

  #main_banner h1{
    color: #fff;
    text-align: center;
    font-size: 60px;
    background-color: #222;
    padding: 20px 40px;
  }
</style>
