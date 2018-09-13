<template>
    <div class="modal is-active">
  <div class="modal-background"></div>
  <div class="modal-content">
    <div class="container is-fluid">
  <div class="notification">
    <h1> </h1>
    <h2> Título: <input type="text"  v-model="nuevoTitulo"> </h2>
    <h2> Descripción: <textarea class="textarea" placeholder="Descripción de la tarea" rows="4" v-model="descripcionTarea"></textarea></h2>
  </div>
</div>
</div>
{{nuevaTarea.descripcion}}
  <button class="modal-close is-large" aria-label="close"></button>
</div>
</template>

<script>
export default {
    name: 'modal',
    data(){
        return{
        nuevoTitulo: '',
        descripcionTarea: '',
        }

    },
    props: {
        nuevaTarea: {
            type: Object,
            required: true
        }
    },
}
        
     


</script>

<style>

</style>
