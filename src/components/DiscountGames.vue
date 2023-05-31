<script>
import axios from 'axios';
export default {
  name: 'DiscountGames',
  data() {
    return {
      apiBaseUrl: 'http://127.0.0.1:8000/api',
      apiUrls: {
        discounts: '/games/discount'
      },
      discounts:[],
    }
  },
  methods: {
    getGame() {
      axios.get(this.apiBaseUrl + this.apiUrls.discounts)
        .then((response) => {
          this.discounts = response.data.results.data;
          console.log(this.discounts);
        })
    }
  },
  created() {
    this.getGame();
  }
}
</script>

<template>

  <div class="ms-container mb-5" v-if="discounts">
    <div class="row">
    <h4 class="mb-4">OFFERTE SPECIALI </h4>
    <div class="card-game-disc col-4" v-for="discount in discounts">
      <div class="img">
        <img :src="discount.image" alt="">
      </div>
      <div class="price">
        <h4>PREZZo</h4>
      </div>
    </div>
  </div>
</div>
</template>

<style lang="scss" scoped>
@use '../assets/scss/_partial/_variables' as *;
h4{
  color: white;
}
.ms-container{
margin: 0 auto;

.card-game-disc {


  .img {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    height: 100%;
    img {
      width: 100%;

       object-fit: cover;
    }
  }
}
}

</style>