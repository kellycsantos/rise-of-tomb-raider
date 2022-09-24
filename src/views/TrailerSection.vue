<template>
  <div class="trailer-section">
    <div class="story-content">
      <slot></slot>
      <slot name="platform"></slot>
      <slot name="parcerias"></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TrailerSection',
  components:{},
  data(){
    return{
      story:null
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.trailer-section{
 background: url('../assets/background/background-secondary.png') no-repeat #000;
 background-size: 100% 100%;
 display: flex;
 flex-direction: column;
 justify-content: center;
 align-items: center;
 max-height: max-content; 
 padding: 50px;
 color: #000;
}

.story-content{
  width: 75vw;
  padding: 25px 50px;
}

@media screen and (min-width:768px) {
  .initial-section{
 height: 30vh; 
}

.story-content{
  width: 60vw;
  padding: 25px 50px;
}
}
</style>
