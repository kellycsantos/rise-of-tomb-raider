<template>
  <div v-for="(data, index) in data" :key="index">
    <InitialSection id="home" />
    <StorySection id="story">
      {{data.story}}
    </StorySection>
    <TrailerSection id="resume">
      <div>
        <h2>Sinopse</h2>
      </div>
      <div>{{data.resumo}}</div>
      <iframe class="ytplayer" type="text/html" :src="data.trailer[1]" frameborder="0"></iframe>
    </TrailerSection>
    <WeaponsSection @prev="prev" @next="next" id="armas">
      <div class="weapon-container">
        <h3>{{data.weapons[imgIndice].name}}</h3>
        <img class="weapon-img" :src="data.weapons[imgIndice].img" />
      </div>
    </WeaponsSection>
    <ReleaseSection id="release">
      <template v-slot:release-date>
        <h2>{{date }}</h2>
      </template>
    </ReleaseSection>
    <TrailerSection class="release-section" id="release">
      <template v-slot:platform>
        <div class='icon'>
          <img v-for="(plat,index) in data.platforms" :key="index" :src="plat.icon">
        </div>
      </template>
    </TrailerSection>
    <FooterSection>
      <a v-for="(social, index) in data.social" :key="index" :href="social.link" target="_blank">
        <img :src="social.icon" class="icon-social">
      </a>
    </FooterSection>

  </div>
</template>

<script>

import axios from 'axios'
import moment from 'moment'

import InitialSection from './views/InitialSection.vue'
import StorySection from './views/StorySection.vue';
import WeaponsSection from './views/WeaponsSection.vue';
import TrailerSection from './views/TrailerSection.vue';
import ReleaseSection from './views/ReleaseSection.vue';
import FooterSection from './views/FooterSection.vue'
export default {
  name: 'App',
  components: {
    InitialSection,
    StorySection,
    WeaponsSection,
    TrailerSection,
    ReleaseSection,
    FooterSection
  },
  data() {
    return {
      data: null,
      imgIndice: 0,
      trailer: 'https://www.youtube.com/embed/iXWyo4Lgo44',
      trailee: "https://www.youtube.com/embed/1_FIyNcQSgA",
      date: null
    }
  },
  methods: {
    async getData() {
      await axios
        .get('https://rotr-api.onrender.com')
        .then(res => this.data = res.data.data)
        .then(date => this.date = date[0].release)

      if (this.date != null) {
        this.date = moment(this.date).format("DD/MM/YYYY")
      }
    },
    prev() {
      if (this.imgIndice > 0) {
        return this.imgIndice--
      }
    },
    next() {
      if (this.imgIndice < this.data[0].weapons.length - 1) {
        return this.imgIndice++
      } else {
        this.imgIndice = 0
      }
    }
  },
  beforeMount() {
    this.getData()
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #f2f2f2;
  height: 100vh;
  background: black;
}

.ytplayer {
  min-width: 60vw;
  min-height: 50vh;
  margin: 50px 0;
}

.weapon-img {
  width: 45vw;
  max-height: 200px;
  max-width: 400px;
  display: flex;
  align-self: center;
  justify-self: center;
}

.weapon-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-evenly;
  width: 65vw;
  height: 30vh;
  font-size: x-large;
}



.release-section {
  min-height: 15vh;
}

.release-section h2 {
  font-size: xx-large;

}

.icon {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}

.icon img {
  width: 80px;
  margin: 5px;
}

.icon-social {
  margin: 5px;
}
</style>
