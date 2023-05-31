<script>

import axios from 'axios';

export default {
  name: 'GamesList',
  data() {
    return {
      apiBaseUrl: 'http://127.0.0.1:8000/api',
      apiUrls: {
        games: '/games'
      },
      games: [],
    }
  },
  methods: {
    getGame() {
      axios.get(this.apiBaseUrl + this.apiUrls.games)
        .then((response) => {
          this.games = response.data.results.data;
        })
    }
  },
  created() {
    this.getGame();
  }
}

</script>

<template>
  <!-- Main-container-background -->
  <div class="background_color d-flex justify-content-center align-items-center">
    <!-- container-cards -->
    <div class="d-flex justify-content-center">
      <div>
        <!-- Titolo -->
        <div class="color_general px-2">
          <h1>I GIOCHI</h1>
        </div>
        <!-- Titolo -->
        <!-- ------------------------------------------------------------------------------------ -->
        <!-- Singola Card -->
        <div class=" container-fluid d-flex justify-content-center py-1" v-for="game in games">
          <div class="d-flex container_card ">
            <!-- img -->
            <div class="container_img">
              <img class="" src="https://picsum.photos/420/210" alt="" srcset="">
            </div>
            <!-- img -->
            <!-- Info -->
            <div class="d-flex main_container_info ">
              <!-- container-left-info -->
              <div class="container_info">
                <div class="py-1">
                  <h2 class="px-3 color_title">{{ game.title }}</h2>
                </div>
                <div class="d-flex px-3 py-1">
                  <div>
                    <h6 class="py-1 px-1 genre">generi</h6>
                  </div>
                  <div class="px-2">
                    <h6 class="py-1 px-1 genre">generi</h6>
                  </div>
                </div>
                <div class="py-1">
                  <h6 class="px-3 publisher_date">Data e Anno</h6>
                </div>
              </div>
              <!-- container-left-info -->
              <!-- container-right-info -->
              <div class="container_info_due d-flex align-items-end py-2">
                <div class="sale py-1">
                  <h1>-50%</h1>
                </div>
                <div class="freetoplay py-1 px-2">
                  <div class="old_price d-flex justify-content-end ">$29.99</div>
                  <div class="sale_price">$19.99</div>
                </div>

              </div>
              <!-- container-right-info -->
            </div>
            <!-- Info -->
          </div>
        </div>
        <!-- Singola Card -->
        <!-- ------------------------------------------------------------------------------------ -->
      </div>
    </div>
    <!-- container-cards -->
  </div>
  <!-- Main-container-background -->
</template>

<style lang="scss" scoped>
.background_color {
  background: rgb(66, 75, 90);
  background: linear-gradient(90deg, rgba(66, 75, 90, 1) 0%, rgba(66, 75, 90, 1) 20%, rgba(72, 85, 101, 1) 55%, rgba(75, 91, 106, 1) 100%);
  width: 100%;
  height: 90.625rem;
}

.container_card {
  width: 90.625rem;
  max-height: 13.4375rem;
  background-color: #404853;
  border-radius: .3125rem;
  position: relative;
  overflow: hidden;
}

.container_card::after {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 4px;
  background-image: linear-gradient(to right, transparent, #353d47);
}

.main_container_info {
  width: 70%;
}

.container_img {
  width: 30%;
}

.container_info {
  width: 80%;
}

.container_info_due {
  width: 20%;
}

.genre {
  background-color: #49515c;
  color: #bec6d1;
  border-radius: .3125rem;
  transition: transform 0.2s ease, background-color 0.2s ease;
  cursor: pointer;
}

.genre:hover {
  background-color: #3d5f8d;
  transform: scale(1.1);
}

.publisher_date {
  color: #bec6d1;
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
  font-size: 14px;
  text-decoration: none;
  color: #56656c;
}

.old_price::after {
  content: "";
  position: absolute;
  top: 50%;
  left: 25px;
  width: 70%;
  height: 2px;
  background: #56656c;
  transform: rotate(-20deg);
}

.sale_price {
  font-size: 1.5rem;
  text-decoration: none;
  color: #b7de33
}
</style>
