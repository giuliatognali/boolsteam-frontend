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

        <div class="color_general">
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

            <div class="d-flex ">

              <!-- container-left-info -->

              <div class="container_info">

                <div class="">
                  <h2 class="px-3 color_title">{{ game.title }}</h2>
                </div>
                <div class="d-flex px-3">
                  <div>
                    <h6 class="py-1 px-1 genre">generi</h6>
                  </div>
                  <div class="px-2">
                    <h6 class="py-1 px-1 genre">generi</h6>
                  </div>
                </div>
                <div>
                  <h6 class="px-3 publisher_date">Numero e Data</h6>
                </div>
                
              </div>

              <!-- container-left-info -->

              <!-- container-right-info -->

              <div class="container_info_due d-flex align-items-end py-2">

                <div class="sale py-1">
                  <h1>-50%</h1>
                </div>

                <div class="freetoplay py-1 px-2">
                  <div class="old_price">$29.99</div>
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
  background-color: #424b5a;
  width: 100%;
  height: 93.75rem;
}

.container_card {
  width: 106.25rem;
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
  height: 2px;
  background-image: linear-gradient(to right, transparent, #353d47);
}

.container_img {
  width: 26.25rem;
}

.container_info {
  width: 68.75rem;
}

.container_info_due {
  width: 10.625rem;
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

.sale_price {
  font-size: 1.5rem;
  text-decoration: none;
  color: #b7de33
}

</style>
