<template>
    <v-container>
        <encabezado/>                 <!--introduzco lo que está en Encabezado en la página calculadora-->
        <v-row>
            <v-col>
                <h1 class="text-center">Calculadora Básica</h1>
            </v-col>
        </v-row>

        <v-row>
            <v-col>
                <v-text-field                                    
                    label="Número 1"
                    :rules="rules"
                    hide-details="auto"
                    v-model="n1"
                ></v-text-field>                      <!--entrada de tipo numérica 1-->
            </v-col>
            <v-col>
                <v-text-field                                    
                    label="Número 2"
                    :rules="rules"
                    hide-details="auto"
                    v-model="n2"
                ></v-text-field>
            </v-col>
        </v-row>
        <br>

        <v-row>
            <v-col class="text-center">
                <v-btn                                           
                    color="primary"
                    elevation="11"
                    rounded
                    small
                    @click="suma()"
                >Sumar</v-btn>                             <!--botón Sumar en Beautify-->

                <v-btn                                           
                    color="primary"
                    elevation="11"
                    rounded
                    small
                    @click="resta()"
                >Restar</v-btn> 

                <v-btn                                           
                    color="primary"
                    elevation="11"
                    rounded
                    small
                    @click="multiplica()"
                >Muliplicar</v-btn> 

                <v-btn                                           
                    color="primary"
                    elevation="11"
                    rounded
                    small
                    @click="divide()"
                >Dividir</v-btn>
            </v-col> 
        </v-row>
        
        <br>
        <span>{{ respuesta }}</span>          <!--muestra respuesta interpolado-->

    </v-container>

</template>

<script type="text/javascript">    // Se agrega este type a la etiqueta script para poder imprimir texto en pantalla

import Encabezado from './Encabezado.vue';

export default {
    components: { 
        Encabezado 
    },
    name: "CalculadoraBasica",
    data:()=>{
        return {
            n1: null,                  //Retorna n1
            n2: null,
            respuesta: "", 
            rules: [
                value => !!value || 'Requerido.',
                value => (value && value.length >= 1) || 'Min 1 caracteres',
            ],           
        };
    },
    methods:{
        suma(){
            this.respuesta = parseInt(this.n1) + parseInt(this.n2); 
        },

        resta(){
            this.respuesta = parseInt(this.n1) - parseInt(this.n2); 
        },

        multiplica(){
            this.respuesta = parseInt(this.n1) * parseInt(this.n2); 
        },

        divide(){
            if (parseInt(this.n2) != 0) {
                this.respuesta = parseInt(this.n1) / parseInt(this.n2); 
            } else {
                this.respuesta = window.alert("No se puede dividir por cero");
            }
        }

    }

}
</script>

<style>

</style>