<script>
export default {
  name: 'CardTopMain'
}
</script>

<template>
  <div class="card-game-main col-4 mt-5">
    <div>
      <img src="https://picsum.photos/id/237/300" alt="">
    </div>
    <div class="icon">
      <i class="fa-solid fa-star pt-2" ></i>
      <h3></h3>

    </div>
    <div class="discount-price">
      PREZZO
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use '../assets/scss/_partial/_variables' as *;

.card-game-main {
  height: 27.5rem;
  margin-left: -5px;
  position: relative;


  div {
    background-color:hsla(0, 0%, 50%, 0.4);
    height: 100%;
    display: flex;
    justify-content: center;

    img {
      height: 100%;
      width: 80%;
      object-fit: cover;
    }
  }
.discount-price{
  position: absolute;
    height: 40px;
    width: 40px;
    bottom: 0px;
    right: 20px;

}
  .icon {
    background-color: #0d6593;
    position: absolute;
    height: 40px;
    width: 40px;
    top: 0px;
    right: 10px;
    font-size: 18px;
    i{
      display: block;
    }
  }
}
</style>
