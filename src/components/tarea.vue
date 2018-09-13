<template>
    <button class="button is-success is-fullwidth" @click="mostrarTarea" >  {{nuevaTarea.titulo}}  </button>
</template>

<script>
export default {
    name: 'tarea',
    

    props: {
        nuevaTarea:{
            type: Object,
            required: true
        }
    },
    methods: {
        mostrarTarea(){
            this.$root.$emit('mostrar-Tarea', this.nuevaTarea);
           
        }
    }

}
</script>

<style>

</style>
