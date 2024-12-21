<template>
  <!--   estrutura de mi pagina, aqui va la pregunta y el API va a responder si es Verdadero o Falso -->
  <img :src="imagen" alt="No se puede Visualizar" />
  <input v-model="pregunta" type="text" placeholder="Hazme una pregunta.." />
  <p>Recuerda que cuando finalices tu pregunta dar un ?</p>
  <h1>{{ pregunta }}</h1>
  <h2>{{ respuesta }}</h2>
</template>

<script>
export default {
  data() {
    return {
      pregunta: "Hola Mundo",
      respuesta: null,
      imagen:
        "https://yesno.wtf/assets/no/26-34b31d1f0777f70c61488f67a36576a9.gif",
    };
  },
  watch: {
    pregunta(value, oldValue) {
      console.log(value);
      console.log(oldValue);
      if (value.includes("?")) {
        //programar la llamada al API para obtener el Si o No, y la imagen
        console.log("Aqui Llamar la API");
        this.fachada();
      }
    },
  },
  methods: {
    async llamarAPI() {
      //Aqui va la llamada al API
      //lo guardamos en  unca constante data porque se mantendra intacto
      //simepre que llamamos un API siempre se debe poner la palabra reservada await y poner el mentodo async (asincrono)
      const data = await fetch("https://yesno.wtf/api").then((r) => r.json());
      this.respuesta = data.answer;
      this.imagen = data.image;
      console.log(data);
    },
    async fachada(){
        await this.llamarAPI();
    }
  },
};
</script>

<style>
</style>