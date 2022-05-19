<template>
  <div>
    <h1> Hello {{ name }}!</h1>
    <h2 v-if="isUserConnected">Vous êtes connecté</h2>
    <h2 v-else>Veuillez vous connecter</h2>
    <h3 v-show="isUserConnected">Content de vous revoir !</h3>


    <!-- <div>{{ contenuHTML }}</div> -->
    <div v-html="contenuHTML"></div>

    <form action="" @submit.prevent="onFormSubmit">
      <!-- <input type="text" name="machin" id="machin" v-bind:value="nomPromo"> -->
      <input type="text" name="machin" id="machin" v-model="nomPromo">
      <button role="submit">Valider</button>
    </form>

    <ul>
      <!-- <li v-for="fruit in fruitList">{{ fruit }}</li> -->
      <li v-for="fruit in fruitList" v-bind:key="fruit.id">{{ fruit.name }}</li>
    </ul>


    <CustomFooter :today="currentDay"></CustomFooter>
  </div>

</template>

<script>
import CustomFooter from './components/CustomFooter.vue';

  export default {
    data() {
      return {
        name: "Vue",
        contenuHTML: "<strong>Bienvenous à Vue</strong>",
        nomPromo : "",
        fruitList: [
          {id: 1, name: "pommes"},
          {id: 2, name: "poires"},
          {id: 3, name: "fraises"},
          {id: 4, name: "raisins"}
        ],
        isUserConnected: false,
        currentDay: "18/05/2022"
      };
    },
    methods: {
      onFormSubmit(event) {
        console.log("Le nom de la promo est " + this.nomPromo);
      }
    },
    components: {
      CustomFooter
    }
  };
</script>