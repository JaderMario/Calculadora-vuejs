<template>
  <div>
    <h2>This is an about page</h2>
    <calculadora-basica/>
  </div>
</template>

<script>
//Importamos CalculadoraBasica.vue a la vista About,       ../ remplaza a scr 
import CalculadoraBasica from '../components/CalculadoraBasica.vue'     

export default {
  name: 'About',
  components: {
    CalculadoraBasica
  }
}
</script>