<template>
  <div id="app">
    <h1>Crea una nueva tarea</h1>

    <label>Tarea </label>
    <input v-model="nuevaTarea" placeholder="Ingresa una nueva tarea">
    <button @click="agregarTareas">Crear</button>
    <div>
    <List :tareas="tareas" @eliminarTarea="eliminarTarea"/>
    </div>
  </div>
</template>

<script>
import List from './components/List.vue'

export default {
  name: 'App',
  components: { List },
  data: () => ({
    nuevaTarea: "",
    tareas: [],
  }),

  methods: {
    agregarTareas: function(){
      this.tareas.push(this.nuevaTarea)
      this.nuevaTarea = ""
    },
    eliminarTarea: function($index) {
      this.tareas.splice($index, 1)
    }
  },
};
</script>

<style scoped>
  #app {
    font-family: Arial, Helvetica, sans-serif;
    text-align: center;
  }
</style>