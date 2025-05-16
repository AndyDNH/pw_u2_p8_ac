<template>
  <div class="container">
    <h1>{{ title }}</h1>
    <p>{{ numero }} <sup>2</sup>={{ calCuadrado }}</p>
    <!-- <p>{{numero}} <sup>2</sup>={{ calCuadrado}}</p>
    <p>{{numero}} <sup>2</sup>={{ calCuadrado }}</p>
    <p>{{numero}} <sup>2</sup>={{ calCuadrado}}</p>
    <p>{{ calCuadrado }}</p> -->

    <div>
      <button v-on:click="incrementar()">+1</button>
      <!-- Shortcut de v-on -->
      <button @click="decrementar()">-1</button>
    </div>

    <!-- <h3>{{ texto }}</h3>
    <p>{{ activo }}</p>
    <h3>{{usuario.Genero}}</h3>
    <p>{{ arreglo }}</p>
    {{ numero +1 }}
    <br>
    {{false?'Es verdadero': 'Es Falso'}} -->
  </div>
</template>

<script>
export default {
  // forma 1 de declarar props
  // props:['title','value'],
  // Segunda forma de declarar props(declaracion explicita del tipo de dato)
  props: {
    title: String,
    // detallando la descripcion del prop
    value: {
      type: Number,
      // required me dice si el valor es requerdo para ser usado pero si es falso pasa a 
      // tomar el valor por defecto defindo
      required: false,
      default: 100,
      // puedo enviar una unica validacion por prop
      validator(value){
        return value>0
      }
    },
    p1: Boolean,
    p2: Array,
    p3: Object,
    p4: Function,
    p5: Date,
    // Para envio de tokens
    p6: Symbol,
  },
  data() {
    return {
      numero: this.value,
      titulo: "Contador",
      texto: "Andres Cueva",
      activo: true,
      usuario: {
        nombre: "Andres",
        apellido: "Cueva",
        Genero: "Masculino",
      },
      arreglo: ["amarillo", "azul", "verde"],
    };
  },
  methods: {
    calcularCuadrado() {
      console.log("Entro Al metodo");
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
    calCuadrado() {
      console.log("Entro a Propiedad Computada");
      return this.numero * this.numero;
    },
  },

  // Artificio para que la no pueda continuar si no cumplo con la validacion
  created(){
    if(this.value>0){
      console.log('Es Correcto')
    }else{
      throw new Error('No puede ser 0')
    }
  },
};
</script>

<style>
</style>