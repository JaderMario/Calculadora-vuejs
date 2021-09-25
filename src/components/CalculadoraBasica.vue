<template>
    <div>
        <h1>Calculadora Básica</h1>

        <v-text-field                                    
            label="Número 1"
            :rules="rules"
            hide-details="auto"
            v-model="n1"
        ></v-text-field>                      <!--entrada de tipo numérica 1-->

        <v-text-field                                    
            label="Número 2"
            :rules="rules"
            hide-details="auto"
            v-model="n2"
        ></v-text-field>
        <br>

        <v-btn                                           
            color="primary"
            elevation="11"
            rounded
            small
            @click="suma()"
        >Sumar</v-btn>                                    <!--botón Sumar en Beautify-->   

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
        
        <br>
        <span>{{ respuesta }}</span>          <!--muestra respuesta interpolado-->

    </div>

</template>

<script type="text/javascript">    // Se agrega este type a la etiqueta script para poder imprimir texto en pantalla
export default {
    name: "CalculadoraBasica",
    data:()=>{
        return {
            n1: null,                  //Retorna n1
            n2: null,
            respuesta: "", 
            rules: [
                value => !!value || 'Requerido.',
                value => (value && value.length >= 3) || 'Min 3 caracteres',
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
                this.respuesta = document.write("No se puede dividir por cero");
            }
        }

    }

}
</script>

<style>

</style>