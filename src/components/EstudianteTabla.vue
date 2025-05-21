<template>
  <div class="container">

    <transition>
      <div v-show="mostrar" class="confirmacion">
        <h1>Empresa Registrada</h1>
      </div>
    </transition>

    <div class="textos">
      <label for="id_nombre">Nombre de la Compañia</label>
      <input v-model="nuevoNombre" id="id_nombre" type="text" />

      <label for="id_direccion">Direccion</label>
      <input v-model="nuevoDireccion" id="id_direccion" type="text" />

      <label for="id_contacto">Numero de Contacto</label>
      <input v-model="nuevoContacto" id="id_contacto" type="tel" />

      <label for="id_representante">Representante Legal</label>
      <input v-model="nuevaRepresentante" id="id_representante" type="text" />

      <label for="id_medio">Medio de envio</label>
      <input v-model="nuevoTransporte" id="id_medio" type="text" />

    </div>

    <br />
    <button v-on:click="agregarEmpresa"><b>Agregar</b></button>



    <table border="1">
      <thead>
        <!--tr siempre es primero y representa una fila, primero se contruye tanto en la cabecera como el cuerpo-->
        <tr>
          <!--Como contenido de la fila declaro todas las columnas-->
          <th>Nombre</th>
          <th>Direccion</th>
          <th>Contacto</th>
          <th>Representante</th>
          <th>Transporte</th>

        </tr>
      </thead>
      <tbody>
        <tr v-for="{ nombre, direccion, contacto, representante, transporte } in lista" :key="nombre + direccion">
          <!--Para la columna ya no declaro un th si no que un elemento td-->
          <td>{{ nombre }}</td>
          <td>{{ direccion }}</td>
          <td>{{ contacto }}</td>
          <td>{{ representante }}</td>
          <td>{{ transporte }}</td>

        </tr>
        <!--Por cada fila es un elemento html tr-->

      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nuevoNombre: "",
      nuevoDireccion: "",
      nuevoContacto: "",
      nuevaRepresentante: "",
      nuevoTransporte: "Auto",
      lista: [
        {
          nombre: "Schneider Electric",
          direccion: "Av. de los Shyris",
          contacto: "0983999231",
          representante: "Oswaldo León",
          transporte: "Auto",
        },
        {
          nombre: "Corporación Favorita C.A. ",
          direccion: "Av. 6 de Diciembre y Eloy Alfaro",
          contacto: "0922318399",
          representante: "Rubén Salazar",
          transporte: "Carguero",
        },
        {
          nombre: "CNT EP",
          direccion: "Av. 9 de Octubre y García Avilés",
          contacto: "0962945123",
          representante: "Darwin Romero",
          transporte: "Avion",
        },
        {
          nombre: "Pronaca ",
          direccion: "Vía Quevedo km 6.5, Santo Domingo",
          contacto: "0991235673",
          representante: "Luis Bakker",
          transporte: "Auto",
        },
        {
          nombre: "Banco Pichincha",
          direccion: "Av. Remigio Crespo y Av. Solano",
          contacto: "0994336711",
          representante: "Santiago Bayas",
          transporte: "Avion",
        },
        {
          nombre: "Ambacar Cía. Ltda.",
          direccion: "Av. Indoamérica Km 1.1, Ambato",
          contacto: "0998877213",
          representante: "Esteban Inta",
          transporte: "Carguero",
        },
        {
          nombre: "Corporación Azende",
          direccion: "Vía Cuenca – Paute km 2.5",
          contacto: "0993344121",
          representante: "Gabriel Allende",
          transporte: "Auto",
        },
      ],
      mostrar: false,
    };
  },
  methods: {
    agregarEmpresa() {
      const nuevo = {
        nombre: this.nuevoNombre,
        direccion: this.nuevoDireccion,
        contacto: this.nuevoContacto,
        representante: this.nuevaRepresentante,
        transporte: this.nuevoTransporte,
      };
      // this.lista.unshift(nuevo);
      this.lista.push(nuevo);
      this.mostrar = true;
      this.nombre = null;

      setTimeout(() => {
        this.mostrar = false;
      }, 2000);
    },
  },
};
</script>

<style>
li {
  font-size: 20px;
}

.container {
  background: #edf7f6;
  border: 1px solid;
  border-radius: 12px;
  max-width: 900px;
  /* auto coloca el mismo valor a la derecha como a la izq */
  margin: 50px auto;
  padding: 30px;
}



.confirmacion {
   background: #4e91f9;
  color: #fff;
  padding: 8px 16px;
  border-radius: 6px;
  text-align: center;
  font-size: 14px;
  width: fit-content;
  margin: 0 auto 20px auto;
  box-shadow: 0 2px 8px black;
}

label {
  display: block;
  color: #333;
  text-align: left;
  padding-left: 75px;
}

input {
  background: #4e91f9;
  color: #fff;
  width: 80%;
  border-radius: 8px;
  margin-bottom: 10px;
  border: 1px solid #ddd;
  padding: 10px 15px;
  text-align: left;
}

button {
  background: #4e91f9;
  color: #fff;
  padding: 12px 10px;
  font-size: 20px;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  width: 120px;
}

table {
  width: 95%;
  border-collapse: separate;
  border-spacing: 0;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  font-size: 0.95rem;
  background-color: #fff;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.05);
  border-radius: 8px;
  overflow: hidden;
  margin: 20px auto;
  /* padding: 0 20px; */


}

thead {
  background-color: #f4f6f8;
}

thead th {
  text-align: center;
  padding: 15px;
  color: #333;
  font-weight: 600;
  border-bottom: none;
}

tbody tr {
  transition: background-color 0.2s;
}

tbody tr:nth-child(even) {
  background-color: #7bacdd;
}

tbody tr:hover {
  background-color: #9da0a5;
}

tbody td {
  padding: 15px;
  border-bottom: 1px solid #e3e6ea;
  color: #444;
}
</style>