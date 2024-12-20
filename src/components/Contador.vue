<template>
  <h2>{{ encabezado }} : {{ valor2 }}</h2>
  <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputed }}</p>
  <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputed }}</p>

  <div>
    <button @:click="incrementar()">+1</button>
    <button v-on:click="decrementar()">-1</button>
  </div>
  <div v-if="esVerdad">
    <h1>Feliz Navidad</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero: this.valor,
      titulo: "Contador",
    };
  },
  methods: {
    calcularCuadrado() {
      console.log("Método Entro a calcular");
      return this.numero * this.numero;
    },
    incrementar() {
      this.numero++;
    },
    decrementar() {
      this.numero--;
    },
  },
  computed: {
    calcularCuadradoComputed() {
      console.log("Computed Entro a calcular");
      return this.numero * this.numero;
    },
  },
  //Primera forma de declaracion de un props
  //props: ['encabezado', 'valor'],

  //Segunda forma de declaracion de un props
  props: {
    //validar encabezado, solo si no contiene la letra "a"
    encabezado: {
      type: String,
      required: true,
      validator(value) {
        return !value.includes("a");
      },
    },
    // encabezado: String,
    valor: Number,
    valor2: {
      type: Number,
      required: false,
      default: 77,
      validator(value){
        //programo mi validacion bajo mi criterio y retorno true
        //cuando es valido para mi y retorno false cuando no es valido
        return value <=77;

      }
    },
    esVerdad: {
      type: Boolean,
      required: true,
    },
    arreglo: Array,
    fecha: Date,
    objetoPersona: Object,
  },
};
</script>

<style>
button {
  background: #64b687;
  border-radius: 5px;
  border: 1px solid blue;
  color: white;
  cursor: pointer;
  margin: 0px 10px;
  padding: 12px 20px;
}
button:hover {
  background: #40895f;
}
</style>