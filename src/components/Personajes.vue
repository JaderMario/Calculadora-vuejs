<template>

  <div>
    <h1>Personajes</h1>
    <ul>
      <li v-for="item in personajes" :key="item.Name">
        {{item.Name}}
      </li>
    </ul>
  </div>

</template>

<script>
import store from "../store/index.js";

export default {
  data: () => {
    return{};
  },
  methods: {},
  created: () => {
    //Accede a las acciones (actions) del store, voy a getPersonajes para traer la API futurama
    store.dispatch("getPersonajes");       
  },
  computed: {
    personajes: () => {
      return store.state.personajes;
    },
  },
};

</script>

<style>
h1 {
  color: blue;
  text-align: center;
}
</style> 