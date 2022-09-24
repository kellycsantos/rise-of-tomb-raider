<template>
  <div class="initial-section">
    <TheMenu />
  </div>
</template>

<script>
import TheMenu from '../components/TheMenu.vue';
export default {
  name: 'HelloWorld',
  components: {
    TheMenu,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.initial-section {
  background: url('../assets/background/background-tomb-raider.png') no-repeat;
  background-size: cover;
  background-position-x: 50%;
  height: 95vh;
}

@media screen and (min-width: 768px) {
  .initial-section {
    background: url('../assets/background/background-tomb-raider.png') center no-repeat;
    background-size: 100vw 100vh;
  }

}
</style>
