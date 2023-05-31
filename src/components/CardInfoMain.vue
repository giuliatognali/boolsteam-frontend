<script>
export default {
  name: 'CardInfoMain'
}
</script>

<template>
<div class="card-info mt-5 col-8 p-2">
  <h2>Titolo </h2>
  <h3>Data di rilascio: data</h3>
  <p>Descrizione: Lorem ipsum dolor, sit amet consectetur adipisicing elit. In recusandae ex perspiciatis magnam deleniti? Corporis, ab, facilis nihil iste amet, vero ullam eius aliquam laborum fugiat aperiam aliquid odio quasi.</p>
  <div class="tags" ><!-- v-for="types in tyep" o una roba del genere -->
  
  <span class="badge bg-secondary">Tipologie</span><span class="badge bg-secondary">Tipologie</span>
  <span class="badge bg-secondary">Tipologie</span><span class="badge bg-secondary">Tipologie</span>
  <span class="badge bg-secondary">Tipologie</span><span class="badge bg-secondary">Tipologie</span>

</div>
  </div>
  
</template>

<style lang="scss" scoped>
  @use '../assets/scss/_partial/_variables' as *;

.card-info{
  background-color:hsla(0, 0%, 50%, 0.4);
  height: 27.5rem;

}
.tags{
margin-left: -5px;
}
span{
  font-size: 1rem;
  margin: 5px;
  border-radius: 0;
}
</style>
