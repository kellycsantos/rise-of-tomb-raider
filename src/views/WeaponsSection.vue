<template>
  <div class="weapons-section">
    <div class="weapons-elements">
    <button class="button prev" @click="prev"></button>
    <slot></slot>
    <button class="button next" @click="next"></button>
  </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'WeaponsSection',
  components: {
  },
  methods: {
    async getData() {
      await axios
        .get('https://rotr-api.onrender.com')
        .then(res => this.story = res.data.data[0].story)
    },
    prev(){
      this.$emit('prev')
    },
    next(){
      this.$emit('next')
    }

  },
  mounted() {
    this.getData()
  }
}
</script>

<style scoped>
  *{
    outline: none;
    box-sizing: border-box;
  }
.weapons-section {
  background: #000000;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: max-content;
  height: 35vh;
}

.weapons-elements{
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100vw;
  max-width: 950px;
  padding: 0 10px;

}

.button{
  width: 50px;
  height: 50px;
  cursor: pointer;
  border: none;
}

.next{
  background: url('../assets/icons/next.png');
  background-size: 100%;
  margin-left: 50px;
  background-repeat: no-repeat;
}

.prev{
  background: url('../assets/icons/prev.png');
  background-size: 100%;
  margin-right: 50px;
  background-repeat: no-repeat;
}

</style>
