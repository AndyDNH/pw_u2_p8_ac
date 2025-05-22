<template>
    <div class="container">
        <img src="https://yesno.wtf/assets/no/19-2062f4c91189b1f88a9e809c10a5b0f0.gif" alt="No se pudo cargar" />
        <div class="container-2">
 
        </div>
        <div class="pregunta-container">
            <input v-model="pregunta" type="text" placeholder="Hazme una pregunta">
            <p>Recuerda terminar con un signo de pregunta (?)</p>
            <h2>{{ pregunta }}</h2>
            <h1>{{respuesta}}</h1>
 
        </div>
 
    </div>
 
</template>
 
<script>
export default {
    data() {
        return {
            pregunta: null,
            respuesta: null,
        };
    },
    watch: {
        pregunta(value, oldValue){
            console.log("Valor actual:" + value);
            console.log("Valor anterior:" + oldValue);
 
        }
 
    }
};
</script>

<style scoped>

.container-2,img {
    /* para que ocupe todo el tamaño  */
    height: 100vh;
    width: 100vw;
    max-height: 100%;
    max-height: 100%;
    /* con position fixed es como si estuviera flotando el elemento como si fuera  */
    /* marca de agua */
    position: fixed;
    left: 0px;
    top: 0px;

}

.container-2 {
    background-color: rgba(97, 13, 194, 0.1);
}

.pregunta-container { 
    position: relative;
}

input {
    width: 250px;
    padding: 10px 15px;
    border-radius: 5px;
    border: none;
    margin-top: 70px;
}
/* para evitar que cuando seleccione el cuadro salga el borde de seleccion */
input:focus {
    outline: none;
}

p {
    color: white;
    font-size: 25px;
}

h1 { 
    color: white;
}

h2 {
    color: white;
    margin-top: 90px;
}

</style>