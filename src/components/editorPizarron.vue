<template>

<div class="editor-tablero">
   <div class="boton">
  <button  class="button is-white  is-medium is-outlined" @click="abrirTablero">
    <p class= "nombrecito-tablero" v-show="nombreGuardado" >
{{nuevoNombre}} 
      </p>
      <p class= "nombre-por-defecto" v-show="nombreDefecto" >
    {{msg}}
        </p>
    
  </button>
  </div>

<div class="tablero">
<article class="message is-info" v-show="tableroAbierto" >
  <div class="message-header">
  Cambiar el nombre del tablero 
 <button class="delete" @click.prevent="cerrarTablero"> </button>
 </div>

 <div class="message-body">
<h2> Nombre:  </h2>
<input type="text" placeholder="New name..." v-model="nombre.titulo">  
<button type="submit" @click.prevent="guardarTitulo" > Cambiar nombre </button>
</div> 
</article>
</div>
</div>

</template>

<script>
export default {
  name: 'editorTablero',
  data() {
    return {
      nombre: {
        titulo: '' 
      },
      tableroAbierto:  false,
      nombreGuadrado: false,
      nuevoNombre: '',
      nombreDefecto: true,
      

    }
    },
    props: {
      msg: {
        type: String
      }
    },
    
    methods: {
      abrirTablero(){
        this.tableroAbierto= true;
      
           },
      cerrarTablero(){
        this.tableroAbierto= false;
      },
      guardarTitulo(){
        this.nombreGuardado= true;
        this.tableroAbierto= false;
        this.nuevoNombre = this.nombre.titulo
        this.nombreDefecto = false
      
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.nombrecito-tablero {
    font-size: 25px
}

.tablero {
  margin-top: 20px
}

</style>