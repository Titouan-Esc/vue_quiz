<template>
  <div id="app">
    <h1>Intro à Vue.js</h1>
    <!-- <p>
      Vue.js est un framwork qui permet de créer du contenu dynamique en
      utilisant un langage similaire à de HTML au niveau du DOM
    </p>
    <p>
      Il permt de jongler avec des données et possède une syntaxe facile à
      prendre en main
    </p>
    <p>
      Vue.js est le plus grand framework JS qui n'est pas le produit d'une méga
      entreprise et est trés prisé des développeurs, car son code est de trés
      grande partie en open source
    </p>
    <p>
      De ce fait; il est le framework JS qui est le plus souvent pris en main
      par les débutants en framework front-end JS mais aussi le framework le
      plus apprécié sur GitHub
    </p> -->
    <p>
      Vue permet d'afficher les données dynamiques comme un compteur avec des
      moustaches \{\{\}\}
    </p>
    <div id="counter">
      <p>Counter: {{ counter }}</p>
    </div>
    <div id="conditional">
      <span v-if="clicks > 10">Calme-toi mon cousin</span>
    </div>
    <p>
      Vue permet de modifier des valeurs en considérant l'intercation
      utilisateur
    </p>
    <button v-on:click="clicked" id="click">
      <p>Clicks: {{ clicks }}</p>
    </button>
    <p>Vue permet aussi de faire de l'affichage conditionnel</p>
    <p>
      Vue permet aussi le 2-way binding, c'est des valeur affichées en temps
      réel qui sont aussi modifiable
    </p>
    <h2>{{ message }}</h2>
    <input v-model="message" />
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      counter: 0,
      clicks: 1,
      message: "Mange tes morts batard",
    };
  },

  mounted() {
    setInterval(() => {
      this.counter++;
    }, 100);
  },
  methods: {
    clicked() {
      this.clicks++;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
