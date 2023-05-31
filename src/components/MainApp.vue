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
  <Jumbo />
  <DiscountGames />
  <GamesList />
</template>

<style lang="scss" scoped></style>
