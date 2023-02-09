<script>

import RatingComponent from './components/RatingComponent.vue';

export default{
  name: "App",
  components:{
    RatingComponent
  }
}

</script>

<template>

  <div class="container">
    <RatingComponent />
  </div>


  <!-- <div class="attribution">
    Challenge by <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">Frontend Mentor</a>. 
    Coded by <a href="#">Your Name Here</a>.
  </div> -->
  
</template>

<style lang="scss">

@use './styles/general.scss';

.container{
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.attribution { font-size: 11px; text-align: center; }
.attribution a { color: hsl(228, 45%, 44%); }

</style>
