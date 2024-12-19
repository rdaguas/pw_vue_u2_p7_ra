<template>
<h2>{{titulo}}</h2>
<p>{{numero}} <sup>2</sup> = {{calcularCuadradoComputed}} </p>
<p>{{numero}} <sup>2</sup> = {{calcularCuadradoComputed}} </p>
<p>{{numero}} <sup>2</sup> = {{calcularCuadradoComputed}} </p>
<p>{{numero}} <sup>2</sup> = {{calcularCuadradoComputed}} </p>
<p>{{numero}} <sup>2</sup> = {{calcularCuadradoComputed}} </p>
<div>
    <button v-on:click="incrementar()">+1</button>
    <button v-on:click="decrementar()">-1</button>
</div>
</template>

<script>
export default {
    data(){
        return{
            numero: 10,
            titulo: 'Contador'
        }
    },
    methods:{
        calcularCuadrado(){
            console.log('Método Entro a calcular');
            return this.numero * this.numero;
        },
        incrementar(){
            this.numero ++;
        },
        decrementar(){
            this.numero --;;
        }
    },
    computed:{
        calcularCuadradoComputed(){
            console.log('Computed Entro a calcular');
            return this.numero * this.numero;
        }
    }
};
</script>

<style>
button{
    background: #64B687;
    border-radius: 5px;
    border: 1px solid blue;
    color: white;
    cursor: pointer;
    margin: 0px 10px;
    padding: 12px 20px;
}
button:hover{
    background: #40895f;
}
</style>