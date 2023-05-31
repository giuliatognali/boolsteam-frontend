<script>
import Jumbo from './Jumbo.vue';
import DiscountGames from './DiscountGames.vue';
import GamesList from './GamesList.vue';

export default {
  name: 'Main',
  components: {
    Jumbo,
    DiscountGames,
    GamesList
  }

}
</script>

<template>
  <main>
    <Jumbo />
    <DiscountGames />
    <GamesList />
  </main>
</template>

<style lang="scss" scoped>
@use '../assets/scss/_partial/_variables' as *;

main {
  background-color: $ms-background ;
}
</style>
