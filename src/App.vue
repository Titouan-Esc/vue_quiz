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
    <ul id="array">
      <li v-for="ho in ho" :key="ho.name">
        {{ ho.name }}, what are is job? {{ ho.job }}
      </li>
    </ul>
    <p>
      Vue permet de créer des composants exportables qui permettent de créer des
      templates prédéfinis et réutilisables "à l'infini"
    </p>
    <p>
      Ces composants peuvent comporter des props, c'est à dire des éléments qui
      varieront en fonction des données qui leur sont attribuées.
    </p>
    <logo
      bienvenue="Ho la con de tes morts"
      v-on:sendBounce="bounces++"
      :bounces="bounces"
    />
    <p>
      Ces props sont assignalbes a des elements dynamiques mais aussi a des
      variables éléments dynalmique qui s'afficheront si ils sont définis et qui
      utiliseront le procédure fallback définis au préalable (dans le cas ou
      aucune fallback procedure n'est définie, l'élément ne s'affichera tout
      simplement pas
    </p>
    <logo :bienvenue="message" />
  </div>
</template>

<script>
import logo from "./components/logo";

export default {
  name: "App",
  components: {
    logo,
  },
  data() {
    return {
      counter: 0,
      clicks: 1,
      message: "Mange tes morts batard",
      ho: [
        { name: "la con de tes morts", job: "démonteur de culasse" },
        { name: "he cousin", job: "éleveur de brebis" },
        { name: "Dede la menace", job: "chauffeur de toro" },
        { name: "Pierre", job: "Caillou" },
        { name: "Didier", job: "Testeur de Ricard" },
        { name: "Jean", job: "On est là" },
      ],
      bounces: 0,
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
