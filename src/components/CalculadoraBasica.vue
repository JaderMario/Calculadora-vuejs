<template>
    <div>
        <h1>Calculadora Básica</h1>
        <input type="number" v-model="n1"/>              <!--entrada de tipo numérica-->
        <input type="number" v-model="n2"/> 
        <br>
        <button @click="suma()">Sumar</button>
        <button @click="resta()">Restar</button>
        <button @click="multiplica()">Multiplicar</button>
        <button @click="divide()">Dividir</button>
        
        <br>
        <span>{{ respuesta }}</span>          <!--muestra respuesta interpolado-->

    </div>

</template>

<script type="text/javascript">
export default {
    name: "CalculadoraBasica",
    data:()=>{
        return {
            n1: null,                  //Retorna n1
            n2: null,
            respuesta: ""              

        }
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