<script>
export default {
  name: 'DiscountGames'
}
</script>

<template>

  <div class="ms-container">
    <div class="row">
    <h4 class="mb-4">OFFERTE SPECIALI </h4>
    <div class="card-game-disc col-4">
      <div class="img">
        <img src="https://picsum.photos/id/247/300" alt="">
      </div>
      <div class="price">
        <h4>PREZZo</h4>
      </div>

    </div>
    <div class="card-game-disc col-4">
      <div class="img">
        <img src="https://picsum.photos/id/247/300" alt="">
      </div>
      <div class="price">
        <h4>PREZZo</h4>
      </div>
    </div>
    <div class="card-game-disc col-4">
      <div class="img">
        <img src="https://picsum.photos/id/247/300" alt="">
      </div>
      <div class="price">
        <h4>PREZZO</h4>
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
    img {
      width: 100%;
/*       height: same-as-width; */
       object-fit: cover;
    }
  }
}
}

</style>