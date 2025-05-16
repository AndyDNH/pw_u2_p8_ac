<template>
    <div class="container">
        <form >
            <label for="id_nombre">Nombre: </label>
            <input id="id_nombre" type="text" v-model="nuevoNombre">
            {{nuevoNombre}}<br/>
            <label for="id_apellido">Apellido: </label>
            <input id="id_apellido" type="text" v-model="nuevoApellido">
            {{nuevoApellido}}<br>
            <label for="id_direccion">Direccion: </label>
            <input id="id_direccion" type="text" v-model="nuevaDireccion">
            {{nuevaDireccion}}<br>
            <label for="id_semestre">Semestre: </label>
            <input id="id_semestre" type="text" v-model="nuevoSemestre">
            {{nuevoSemestre}}<br>
            <label for="id_mail">Email: </label>
            <input id="id_mail" type="text" v-model="nuevoMail">
            {{nuevoMail}}<br>
            <button v-on:click="agregarEstudiante()">Agregar Estudiante</button>
        </form>
        <ul>
            <li v-for="{nombre, apellido, direccion, semestre, mail} in lista" :key="nombre"> Nombre: {{nombre}} 
                - Apellido: {{apellido}} 
                - Direccion: {{ direccion }} 
                - Semestre: {{ semestre }} 
                - Email: {{ mail }}</li>
        </ul>
    </div>  
</template>

<script>
export default {
    data(){
        return{
            nuevoNombre: '',
            nuevoApellido: '',
            nuevaDireccion: '',
            nuevoSemestre: '',
            nuevoMail: '',
            lista: [
                {nombre:"Andres", apellido:"Cueva", direccion:"Madrid oe1", semestre: "primero", mail:"Andres@gmail.com"},
                {nombre:"George", apellido:"Lloa", direccion:"Venezuela", semestre: "segundo", mail:"George@gmail.com"},
                {nombre:"Cait", apellido:"Espinoza", direccion:"La Ecuatoriana", semestre: "tercero", mail:"Cait@gmail.com"},
                {nombre:"Eren", apellido:"Tomala", direccion:"Llano Chivo", semestre: "cuarto", mail:"Eren@gmail.com"},
                {nombre:"Gabriel", apellido:"Armijos", direccion:"EL Roble", semestre: "quinto", mail:"Gabriel@gmail.com"},
                {nombre:"Frida", apellido:"Salas", direccion:"San Juan", semestre: "sexto", mail:"Frida@gmail.com"},
                
            ]
        }
    },
    methods:{
        agregarEstudiante(){
            const nuevo = {
                nombre: this.nuevoNombre,
                apellido: this.nuevoApellido,
                edad: this.nuevaDireccion,
                genero: this.nuevoGenero,
                telefono: this.nuevoTelefono
            }
            
            this.lista.push(nuevo);
            
        }
    }
}
</script>

<style>

</style>