<script>
import axios from 'axios';

export default {
  name: 'CardInfoMain',
  data() {
    return {
      apiBaseUrl: 'http://127.0.0.1:8000/api',
      apiUrls: {
        games: '/games/highlight',
      },
      game: null,
      genres: null
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
<div class="card-info mt-5 col-8 p-2" v-if="game">
  <h2 class="title"><a href="#"> {{game.title}} </a></h2>
  <h3>Data di rilascio: {{game.release_date}}</h3>
  <p>Descrizione: Lorem ipsum dolor, sit amet consectetur adipisicing elit. In recusandae ex perspiciatis magnam deleniti? Corporis, ab, facilis nihil iste amet, vero ullam eius aliquam laborum fugiat aperiam aliquid odio quasi.</p>
  <div class="tags">
  
  <span class="badge " v-for="genre in game.genres">{{genre.name}}</span>

</div>
  </div>
  
</template>

<style lang="scss" scoped>
  @use '../assets/scss/_partial/_variables' as *;

.card-info{
  background-color:hsla(0, 0%, 5%, 0.35);
  height: 27.5rem;
  border-radius: 5px;
.title{
    :hover {
    text-decoration: underline;
    transition: transform 0.7s ease;
  }
}
}
.tags{
margin-left: -5px;
}

span{
  font-size: 1rem;
  margin: 5px;
  background-color: #49515c;
  color: #bec6d1;
  border-radius: .3125rem;
  transition: transform 0.2s ease, background-color 0.2s ease;
  
}
.badge:hover {
  background-color: #3d5f8d;
  transform: scale(1.1);
}
</style>
