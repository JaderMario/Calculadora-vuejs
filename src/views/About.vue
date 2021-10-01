<template>
  <div>
    <h2>This is an about page</h2>
    <!--Componente-->
    <calculadora-basica />
    <!-- Card-->
    <v-card class="mx-auto" max-width="344">
      <v-img
        src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
        height="200px"
      ></v-img>

      <v-card-title> Top western road trips </v-card-title>

      <v-card-subtitle> 1,000 miles of wonder </v-card-subtitle>

      <v-card-actions>
        <v-btn color="orange lighten-2" text @click="inicio()"> Home </v-btn>  <!-- Se agrega un evento con el método inicio(): @clic="inicio()"-->
        <v-spacer></v-spacer>

        <v-btn icon @click="show = !show">
          <v-icon>{{ show ? "mdi-chevron-up" : "mdi-chevron-down" }}</v-icon>
        </v-btn>
      </v-card-actions>

      <v-expand-transition>
        <div v-show="show">
          <v-divider></v-divider>

          <v-card-text>
            I'm a thing. But, like most politicians, he promised more than he
            could deliver. You won't have time for sleeping, soldier, not with
            all the bed making you'll be doing. Then we'll go with that data
            file! Hey, you add a one and two zeros to that or we walk! You're
            going to do his laundry? I've got to find a way to escape.
          </v-card-text>
        </div>
      </v-expand-transition>
    </v-card>
  </div>
</template>

<script>
//Importamos CalculadoraBasica.vue a la vista About,       ../ remplaza a scr
import CalculadoraBasica from "../components/CalculadoraBasica.vue";

export default {
  name: "About",
  components: {
    CalculadoraBasica,
  },
  data: () => ({
    show: false,
  }),
  methods: {
    inicio () {
      console.log("Ir al home...")
      this.$router.push("/")
    }
  }
};
</script>