<template>
  <div class="footer-section">
    <slot></slot>

    <small>Lorem ipsum dolor sit amet consectetur adipisicing elit. Ratione inventore temporibus corrupti dolores
      assumenda aspernatur quibusdam quae accusantium corporis vero, error animi, incidunt velit atque hic ullam
      deserunt quod esse autem amet ipsa natus a ea et? Ex, eligendi, impedit at velit repellendus provident numquam
      distinctio, enim doloribus magni corporis nobis nam eos animi! Sequi eius laborum eaque veniam sapiente nam quod
      beatae magnam numquam, dolor adipisci corrupti veritatis consequuntur in. Itaque alias quidem incidunt impedit
      vero laborum illum unde sit nihil ullam, nesciunt hic.</small>
  </div>
</template>
<script>
export default {
  name: 'FooterSection',
  components: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.footer-section {
  background: #000;
  background-size: cover;
  background-position-x: 50%;
  min-height: 25vh;
  max-width: max-content;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
}

small{
  padding: 20px 45px ;
  color: #8a8787;
}
@media screen and (min-width: 768px) {}
</style>
