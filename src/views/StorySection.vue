<template>
  <div class="initial-section">
    <h1>História</h1>
    <div class="story-content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'StorySection',
  components:{},
  data(){
    return{
      story:null
    }
  },

}
</script>

<style scoped>
.initial-section{
 background: #000000;
 display: flex;
 flex-direction: column;
 justify-content: center;
 align-items: center;
 height: max-content; 
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
