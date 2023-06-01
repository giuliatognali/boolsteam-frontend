<script>
import axios from 'axios';
export default {
  name: 'CardTopMain',
  data() {
    return {
      apiBaseUrl: 'http://127.0.0.1:8000/api',
      apiUrls: {
        games: '/games/highlight',
      },
      game: null,
    }
  },
  methods: {
    getGame() {
      axios.get(this.apiBaseUrl + this.apiUrls.games)
        .then((response) => {
          this.game = response.data.results;

        })
    }
  },
  created() {
    this.getGame();
  }
}
</script>

<template>
  <!-- card heighlight -->
  <div v-if="game" class="card-game-main col-4 mt-5">
    <div class="container_img">
      <a href="#"><img :src="game.image" alt=""></a>
      <!-- icona stella -->
      <div class="icon">
        <div class="border-icon">
          <i class="fa-solid fa-star py-2"></i>
        </div>
      </div>
      <!-- /icona stella -->
      <!-- container price -->
      <div class="container_price d-flex align-items-end py-2">
        <div class="sale py-1">
          <h1>-50%</h1>
        </div>
        <div class="freetoplay py-1 px-2">
          <div class="old_price">$29.99</div>
          <div class="sale_price">$19.99</div>
        </div>
      </div>
      <!-- /container price -->
    </div>
  </div>
  <!-- card heighlight -->
</template>

<style lang="scss" scoped>
@use '../assets/scss/_partial/_variables' as *;

.card-game-main {
  .container_img {
    img {
      height: 450px;
      width: 21.25rem;
      object-fit: cover;

    }
  }
  .icon {
    background-color: #0d6593;
    position: absolute;
    height: 60px;
    width: 60px;
    top: 0px;
    right: 80px;
    font-size: 20px;
    padding: 10px 10px;

    .border-icon {
      background-color: white;
      padding: 0 5px;
      text-align: center;
    }

    i {
      display: block;
      color: #0d6593;
    }
  }

  .container_img {
    position: relative;
  }

  .container_price {
    position: absolute;
    right: 80px;
    bottom: 0;
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
}
</style>
