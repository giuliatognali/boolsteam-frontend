<script>
import CardTopMain from './CardTopMain.vue';
import CardInfoMain from './CardInfoMain.vue';
export default {
  name: 'Jumbo',
  components: {
    CardTopMain,
    CardInfoMain

  }
}
</script>

<template>
  <div class="ms-big-container">
    <div class="ms-container">
      <!-- menu nav -->
      <div class="nav-container">
        <nav class="d-flex justify-content-between">
        <ul class="list-unstyled m-0 d-flex align-items-center">
          <li><a href="#"><h6>Il tuo negozio</h6> </a></li>
          <li><a href="#"><h6>Novità e tendenze</h6> </a></li>
          <li><a href="#"><h6>Categorie</h6> </a></li>
          <li><a href="#"><h6> Negozio e punti</h6></a></li>
          <li><a href="#"><h6>Notizie</h6> </a></li>
          <li><a href="#"><h6>Laboratori</h6> </a></li>
        </ul>
      

        <!-- /menu nav -->
        <!-- search bar -->
        <div class="search-bar">
          <label for="search-game" class="d-none">Cerca</label>
          <input type="text" name="searchGame" id="search-game" class="py-1" placeholder="Cerca">
          <button class="submit btn-secondary px-2 py-1"><i class="fa-solid fa-magnifying-glass"></i></button>
        </div>
      </nav>
    </div>
      <!-- /search bar -->
      <div class="ms-container py-5">
        <h1>
          GIOCHI
        </h1>
        <div class="card-container-jumbo d-flex gap-3">
          <div class="row">
            <CardTopMain />
            <CardInfoMain />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use '../assets/scss/_partial/_variables' as *;

.ms-big-container {
  display: flex;
  margin: 0 auto;
  justify-content: center;
  /*   background: linear-gradient(to right, $ms-background,  transparent), url(/img/jumbo-callofduty.webp);
 */
  background-image: url(/img/jumbo-callofduty.webp);
  background-size: cover;
  background-position: 50% 50%;
  padding: 70px 0px;
  color: white;

  .ms-container {
    width: 100%;

    nav {
      /*   background-color: hsla(210, 39%, 38%, 0.86); */
      background-color: hsla(223, 45%, 52%, 0.831);
      width: 100%;
      margin-top: 0;

      a {
        text-decoration: none;
        color: white;
        padding: 10px 10px;
        display: flex;
        align-items: center;
        height: 100%;

        h6{
          margin: 0;
        }
      }
      a:hover {
              background-color: #8297cc;
            }
    }
  }

  .search-bar {
    padding: 4px 0;
    input{
      border-style: none;
      padding-left: 10px;
      background-color: #336377;
      
      border: 1px darkcyan solid;
    }
    button {
      border-style: none;
      margin-right: 2px;
      background-color: #336377;
      border: 1px darkcyan solid;
    }

}


}</style>
