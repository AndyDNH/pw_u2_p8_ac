<template>
  <div class="container">
    <label for="id_nombre">Nombre</label>
    <input v-model="nuevoNombre" id="id_nombre" type="text"/>
   
    <label for="id_apellido">Apellido</label>
    <input v-model="nuevoApellido" id="id_apellido" type="text"/>
    <button v-on:click="agregarEstudiante">Agregar Edtudiante</button>
    {{ nuevoNombre }}
    <ul>
      <li v-for="{nombre, apellido} in lista" :key="nombre">
        Nombre: {{nombre}} - Apellido: {{apellido}}
     </li>
    </ul>
  </div>
</template>
 
<script>
export default {
  data() {
    return {
        nuevoNombre:"Nuevo",
      lista: [
        { nombre: "Andres", apellido: "Cueva" },
        { nombre: "Tomala", apellido: "Paca" },
        { nombre: "Andy", apellido: "Cueva" },
        { nombre: "Jenny", apellido: "Verde" },
        { nombre: "Jorge", apellido: "Sumi" },
        
      ],
    };
  },
  methods:{
    agregarEstudiante(){
        const nuevo={
            nombre: this.nuevoNombre,
            apellido: this.nuevoApellido,
        };
        // this.lista.unshift(nuevo);
        this.lista.push(nuevo);
 
    },
 
  },
};
</script>
 
<style>

</style>