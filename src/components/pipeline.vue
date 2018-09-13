<template>
<div v-show="lapipeline">
    <div class="card">
        <div class="card-header-title">
            {{nuevaLista.titulo}}
            
           </div>
          
           <div class="card-content">
                 <tarea class="tarea" v-for="tarea in nuevaLista.tareas" :key="tarea.titulo" :nuevaTarea="tarea"/>
     </div>
  <div>
    <div class="editorcito" v-show="editorMostrado" >
        <div class="field"> 
               <div class="control">
    <input class="input is-primary" type="text" placeholder="Título de la tarea" v-model="tituloNuevaTarea"/>
  </div>
</div>

           <button  class="button is-info is-outlined" @click="agregarTarea" > Agregar tarjeta </button>
             </div> 
    </div>
  <footer class="card-footer">
    <p class="card-footer-item">
      <span>
        <button class="button is-black" @click="mostrarEditor"> Agregar tarea </button>
      </span>
    </p>
    <p class="card-footer-item">
      <span>
       <button class="delete" @click="borrarPipeline"></button>
      </span>
    </p>
  </footer>
</div>
</div>
</template>
    


<script>

import tarea from './tarea.vue'
export default {
    name:'pipeline',
   
    data(){
        return{
        tituloNuevaTarea: '',
        editorMostrado: false,
        lapipeline: true
      
        }
    },
    props: {
        nuevaLista:{
            type: Object,
            required: true
        }
        },
         
    methods:{
      agregarTarea(){
            var nuevaTarea = {
                titulo: this.tituloNuevaTarea,
                descripcion: ''
                };
                this.nuevaLista.tareas.push(nuevaTarea);
                this.editorMostrado = false
                
        },
        mostrarEditor(){
          this.editorMostrado = true
        },
        borrarPipeline(){
          this.lapipeline= false
        }
       
    },
    components: {
       tarea
    }


}

</script>


<style>
.tarea{
  margin-bottom: 25px
}

</style>
