<script>
export default {
  name: 'Jumbo'
}
</script>

<template>
  <div class="ms-big-container">
    <div class="ms-container">
      <nav class="d-flex">
        <ul class="list-unstyled m-0 gap-4 d-flex align-items-center">
          <li>Il tuo negozio</li>
          <li>Novità e tendenze</li>
          <li>Categorie</li>
          <li>Negozio e punti</li>
          <li>Notizie</li>
          <li>Laboratori</li>
        </ul>
      </nav>
      <div class="ms-container py-5">
        <h1>
        GIOCHI
      </h1>
      <div class="card-container-jumbo d-flex">
        <div>card 1</div>
        <div>card 2</div>
      </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.ms-big-container{
  display: flex;
  margin: 0 auto;
  justify-content: center;
  background-image: url(/img/jumbo-callofduty.webp);
  background-size: cover;
  padding: 70px 0px;
  color: white;
    .ms-container{
      width: 100%;
      
nav{
  background-color: hsla(210, 39%, 38%, 0.86);
  width: 100%;
  padding: .9375rem 1.25rem ;
}
  }
}
</style>
