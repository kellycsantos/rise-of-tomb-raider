<template>
  <div class="release-section">
    <h2>Lançamento</h2>
    <slot name="release-date"></slot>
    <div class="input-container" v-if="!subscribe">
      <input class="input input-email" type="email" placeholder="Informe seu e-mail" v-model="userEmail">
      <button class="input input-button" :disabled="disabled" @click.once="onSubscribe">Inscrever-se</button>
    </div>
    <div class="subscribe-container" v-else>
      <p> Obrigada por mostrar sua carinho e ansiedade pelo nosso game, não se esqueça de
        verificar a caixa de entrada do endereço eletrônico <span>{{userEmail}}</span>, para estar
        por dentros das novidades de "Rise of <span>Tomb Raider</span>".</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ReleaseSection',
  components: {},
  data() {
    return {
      subscribe: false,
      userEmail: null,
      disabled: true,
    }
  },
  methods: {
    onSubscribe() {
      this.subscribe = true
    }
  },
  watch: {
    userEmail() {
      if (/^\w+([-]?\w+)*@\w+([-]?\w+)*(\.\w{2,3})+$/.test(this.userEmail)) {
        this.disabled = false
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  margin: 0;
  padding: 0;
  outline: none;
  text-decoration: none;
  box-sizing: border-box;
}

.release-section {
  background: #000;
  height: 50vh;
  max-height: max-content;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
}

.release-section h2 {
  font-size: 45px;
  color: #a80016;
}

.input-container {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 150px;
  padding: 10px 0;

}

.input-container .input {
  height: 55px;
  width: 80vw;
  max-width: 600px;
  background: none;
  color: #E5EAED;
  font-size: larger;
  text-align: center;
  text-transform: uppercase;
}

.input-email {
  border: 1px solid #64000d;
}

.input-email:focus {
  color: #ffffff;
  border: 1px solid #e6001f;
}

.input-button {
  border: 1px solid #E5EAED;
  cursor: pointer;
}

.input-button:disabled{
  cursor: no-drop;
  border: 1px solid #7474748a;
 
}

.subscribe-container {
  width: 80vw;
  font-size: x-large;
  word-spacing: 4px;
  line-height: 46px;
}

.subscribe-container p span {
  /* text-decoration: underline; */
  color: #e6001f;
}
</style>
