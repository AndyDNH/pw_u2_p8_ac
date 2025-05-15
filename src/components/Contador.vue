<template>
  <div class="container">
    <h1>Contador</h1>
    <p>{{numero}} <sup>2</sup>={{ calCuadrado }}</p>
    <!-- <p>{{numero}} <sup>2</sup>={{ calCuadrado}}</p>
    <p>{{numero}} <sup>2</sup>={{ calCuadrado }}</p>
    <p>{{numero}} <sup>2</sup>={{ calCuadrado}}</p>
    <p>{{ calCuadrado }}</p> -->

    <div>
      <button v-on:click="incrementar()">+1</button>
      <button v-on:click="decrementar()">-1</button>
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
  data(){
    return {
      numero:5,
      texto: 'Andres Cueva',
      activo:true,
      usuario:{
        nombre: 'Andres',
        apellido: 'Cueva',
        Genero: 'Masculino'
      },
      arreglo:['amarillo','azul','verde'],
    };
  },
  methods:{
    calcularCuadrado(){
      console.log('Entro Al metodo')
      return this.numero*this.numero
    },
    incrementar(){
      this.numero++;
    },
    decrementar(){
      this.numero--;
    }
  },
  computed:{
    calCuadrado(){
      console.log('Entro a Propiedad Computada')
      return this.numero*this.numero
    }
  }
};
</script>

<style>
</style>