_<template>
  <div class="pizarron">
  <editorPizarron msg="Nuevo tablero (clickear para cambiar nombre)"/>
  <div class="pizarron-boton">
    <button class="button is-hovered" @click="agregarLista" > Agregar lista...</button>
  </div>
   <modal v-show="modal"/>

  <div class="pizarron-input" v-show="editorMostrado" >
    <article class="message is-primary">
  <div class="message-header">
    <p>Escribir nombre de la lista</p>
    <button class="delete" aria-label="delete" @click="cancelar"></button>
  </div>
  <div class="message-body">
    <input type="text" v-model="tituloNuevaLista"/>
    <button class="button" @click="crearNuevaLista"> Crear lista </button>
     </div>

</article>
</div>
    
  <div class=" columns">

      <pipeline class="column is-one-third"  v-for="pipeline in pizarron.pipelines" :key="pipeline.titulo" :nuevaLista="pipeline">
     
      </pipeline>
      </div>
      
    </div>
    
</template>

<script>
import editorPizarron from './editorPizarron.vue'
import pipeline from './pipeline.vue'
import modal from './modal.vue'
export default {
  name: 'pizarron',
  data(){
    return{
      pizarron:{
        titulo: '',
        pipelines: []
      },
      tituloNuevaLista: '',
      editorMostrado: false,
      modal: false
      }
  },
  props: {
    nuevoTitulo: {
      type: String,
      required: true
    },
    descripcionTarea: {
      type: String,
      required: true
    },
    nuevaTarea:{
      type: Object,
      required: true
    }
  },
  methods: {
    agregarLista(){
      this.editorMostrado= true
    },
    crearNuevaLista(){
      var nuevaLista ={
        titulo: this.tituloNuevaLista,
        tareas:[]
      };
      this.pizarron.pipelines.push(nuevaLista);
      this.editorMostrado = false
    },
       created(){
      this.$root.$on('mostrar-Tarea', function(nuevaTarea){
        this.modal= true

          
      })
      
       },
       cancelar(){
         this.editorMostrado= false
       }
      },

    components: {
    editorPizarron,
    pipeline,
    modal
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>




</style>
