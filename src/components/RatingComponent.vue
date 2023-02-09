<script>

export default{
  name: "RatingComponent",
  data(){
    return{
      activeRating: 0,
      submitted: false
    }
  },
  methods:{
    submitRating(){
      if(this.activeRating != 0){
        this.submitted = true;
      }
    }
  }
}

</script>

<template>

  
  <div class="rating">
    
    <!-- Rating state start -->
    <div v-if="!submitted" class="rating_state">
      <div class="circle">
        <img src="../assets/images/icon-star.svg" alt="star">
      </div>
      <h3>How did we do?</h3>
      <p>Please let us know how we did with your support request. All feedback is appreciated 
      to help us improve our offering!</p>
      <div class="btn_container">
  
        <div v-for="n in 5" :key="n" @click="activeRating = n" class="circle btn_rating" :class="activeRating == n ? 'active' : ''">{{ n }}</div>
  
      </div>
      <button @click="submitRating">Submit</button>
    </div>

    <!-- Thank you state start -->
    <div v-else class="thank_state">
      <div>
        <img src="../assets/images/illustration-thank-you.svg" alt="Thank You!">
      </div>
      <div class="badge">
        You selected {{ activeRating }} out of 5
      </div>
      <h3>Thank you!</h3>
      <p>We appreciate you taking the time to give a rating. If you ever need more support, don’t hesitate to get in touch!</p>
    </div>

  </div>

  

  <!-- You selected Add rating here out of 5 -->

  <!-- Thank you! -->

  <!-- We appreciate you taking the time to give a rating. If you ever need more support,  -->
  <!-- don’t hesitate to get in touch! -->

  <!-- Thank you state end -->

</template>

<style lang="scss" scoped>

@use '../styles/variables' as *;

.rating{
  background: rgb(37,45,55);
  background: radial-gradient(circle farthest-side at 50% 0%,$dark_blue -20%, $very_dark_blue 180%);
  padding: 35px;
  border-radius: 1.5rem;
  max-width: 412px;
  margin: 25px;
}

h3{
  font-size: 1.6rem;
  margin-top: 30px;
}

p{
  color: $light_grey;
  line-height: 1.3rem;
  margin-top: 15px;
}

.btn_container{
  margin-top: 28px;
  display: flex;
  justify-content: space-between;
}

button{
  cursor: pointer;
  margin-top: 28px;
  border-radius: 50px;
  background-color: $primary_orange;
  color: $white;
  width: 100%;
  padding-block: .8rem;
  text-transform: uppercase;
  letter-spacing: 2px;
  font-weight: bold;
  border: 0;

  &:hover{
    background-color: $white;
    color: $primary_orange;
  }
}

.circle{
  width: 50px;
  height: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 50%;
  background-color: $dark_blue;
  color: $light_grey;
  user-select: none;

  &.btn_rating{
    cursor: pointer;

    &:hover{
      background-color: $primary_orange;
      color: $white;
    }

    &:active,
    &.active{
      background-color: $light_grey;
      color: white;
    }
  }
}

.thank_state{
  text-align: center;

  h3{
    margin-top: 40px;
  }
}

.badge{
  border-radius: 50px;
  background-color: $dark_blue;
  color: $primary_orange;
  padding: 10px 20px;
  width: max-content;
  margin: 30px auto;
}

@media only screen and (max-width: 420px){
  .rating{
    padding: 25px;
  }

  h3{
    font-size: 1.5rem;
  }

  p{
    font-size: .85rem;
  }

  .circle{
    width: 42px;
    height: 42px;
  }

  .thank_state h3{
    margin-top: 18px;
  }
}

</style>
