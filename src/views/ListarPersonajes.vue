<template>
  <personajes />
</template>

<script>
//Importamos Personajes.vue a la vista ListarPersonajes,       ../ remplaza a scr
import Personajes from "../components/Personajes.vue";

export default {
  name: "ListarPersonajes",
  components: {
    Personajes,
  },
};
</script>


<style>

</style>