<script setup>
 import Logo from './components/Logo.vue'
</script>

<script>

export default {
  data() {
    return {

       toggle: true
      
    }
  }
}



</script>

<template>
  <main :class="[toggle ? 'bg-light' : 'bg-dark']">
  <div class="icons">
  <nav>
    <Logo class="logo"></Logo>
  <img class="dark animate__animated animate__rubberBand"  @click = "toggle = !toggle" v-if  = "toggle" src="../public/svg/toggle_on_black_48dp.svg" 
  alt="toggle-dark">
  <img class="light  animate__animated animate__rubberBand " @click = "toggle = !toggle" v-else src="../public/svg/toggle_off_white_48dp.svg" 
  alt="toggle-light">
  </nav>
  </div>
  <div>
  <div class="slider-movie"><h1>SLIDER MOVIE</h1></div>
  </div>
  <div>
    <div class="panel--letter"></div>
  </div>
  
  </main>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap');
/* @import './assets/style.css'; */
:root {

    --font-white:#FFFFFF;

    --letter-correct:#2AA800;

    --bgpanel-guessed-letter:#720303;

    --incorrect-letter:#B70000;

    --gap-panel:black;
}

main {
  width: auto;
  height: 100vh;
}
.bg-light {

background:radial-gradient(ellipse, #dfdfdf 0%, #7b7b7b 100%);;

}
.bg-dark {

  background:radial-gradient(ellipse, #303030 0%, #161312 
    100%);
}
.icons{
  width: 100%;
  display: flex;
  justify-content: flex-end;
  
}
.logo, .slider-movie {
  
}
.slider-movie {
  margin:20px;
}
.logo {
  float: left;
  margin: 20px;
  width: 80px;
}
</style>
