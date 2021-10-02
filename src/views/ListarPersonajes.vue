<template>
  <personajes />
</template>

<script>
//Importamos Personajes.vue a la vista LiatarPersonajes,       ../ remplaza a scr 
import Personajes from "../components/Personajes.vue";

export default {
    name:"ListarPersonajes",
    components: {
        Personajes,
    },
}
</script>

<style>

</style>