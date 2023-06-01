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
      discounts: [],
    }
  },
  methods: {
    getGame() {
      axios.get(this.apiBaseUrl + this.apiUrls.discounts)
        .then((response) => {
          this.discounts = response.data.results.data;
          console.log(this.discounts);
        })
    },
    discountGame(index) {
      const discountGame = this.discounts[index].price * (1 - this.discounts[index].discount);
      return Math.floor(discountGame * 100) / 100;
    },
    percentage(index) {
      const percentage = this.discounts[index].discount * 100
      return percentage;
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
      <div class="card-game-disc col-4" v-for="(discount, index) in discounts">
        <div class="img">
          <img :src="discount.image" alt="">
        </div>

        <div class="container_price d-flex align-items-end py-2">
          <div class="sale py-1" v-if="discount.discount != 0">
                  <h1>-{{ percentage(index) }}%</h1>
                </div>
                <div class="freetoplay py-1 px-2">
                  <div class="old_price d-flex justify-content-end " v-if="discount.price != 0">{{ discount.price }}$</div>
                  <div class="genius d-flex justify-content-center align-items-center" v-else>FREE-TO-PLAY</div>
                  <div class="sale_price" v-if="discount.discount != 0">{{ discountGame(index) }}$</div>
                </div>
        </div>

      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use '../assets/scss/_partial/_variables' as *;

h4 {
  color: white;
}

.ms-container {
  margin: 0 auto;
  padding-bottom: 100px;

  .card-game-disc {


    .img {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      height: 100%;

      :hover {
        transform: scale(1.05);
        transition: transform 0.7s ease;
      }

      :not(:hover) {
        transition: transform 0.7s ease;
        transform: scale(1);
      }

      img {
        width: 100%;

        object-fit: cover;
      }
    }
  }
}

.freetoplay {
  background-color: #2c3640;
  height: 60px;
  border-radius: .125rem;
  color: #bec6d1;
  cursor: pointer;
}

.freetoplay:hover {
  transform: scale(1.1);
}

.sale {
  background-color: #4c6730;
  height: 60px;
  border-radius: .125rem;
  color: #b7de33;
  cursor: pointer;
}

.sale:hover {
  transform: scale(1.1);
}

.color_title {
  color: #bfc3ce;
}

.color_general {
  color: #eef2f5;
}

.old_price {
  position: relative;
  text-decoration: none;
  color: #56656c;
}

.old_price::after {
  content: "";
  position: absolute;
  top: 50%;
  left: 0;
  width: 80%;
  height: 1px;
  background: #56656c;
  transform: rotate(-20deg);
}

.genius {
  background-color: #2c3640;
  text-align: center;
  font-size: 24px;
  height: 2.5rem;
  border-radius: .125rem;
  color: #bec6d1;
  cursor: pointer;
}
</style>