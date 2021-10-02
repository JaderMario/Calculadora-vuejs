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

        <v-row class="text-center">                    <!--centramos todos los botones de la fila-->
            <v-col>                                    <!--Colocamos cada botón dentro de una colummna-->
                <v-btn                                           
                    color="primary"
                    elevation="11"
                    rounded
                    small
                    @click="suma()"
                >Sumar</v-btn>                             <!--botón Sumar en Beautify-->
            </v-col>
            <v-col>
                <v-btn                                           
                    color="primary"
                    elevation="11"
                    rounded
                    small
                    @click="resta()"
                >Restar</v-btn> 
            </v-col>
            <v-col>
                <v-btn                                           
                    color="primary"
                    elevation="11"
                    rounded
                    small
                    @click="multiplica()"
                >Muliplicar</v-btn> 
            </v-col>
            <v-col>
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
        <v-row class="text-center">                      <!--centra la columna-->
            <v-col>
                <v-banner 
                    color="cyan accent-1"                               
                    elevation="13"
                    single-line>
                    <span>{{ respuesta }}</span>          <!--muestra respuesta interpolado-->
                </v-banner>
            </v-col>
        </v-row>
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
                this.respuesta = window.alert(" ¡Error! No se puede dividir por cero");
            }
        }

    }

}
</script>

<style>

</style>