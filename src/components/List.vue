<template>
  <div>
    <h2>Lista</h2>
    <ul>
      <li v-for="(tarea, $index) in tareas" :key="$index">
        {{$index + 1}}: {{tarea}}
        <button @click="eliminarTarea($index)">Eliminar</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'List',
  props: ["tareas"],
  methods: {
    eliminarTarea($index){
      this.$emit("eliminarTarea", $index)
    }
  }
}

</script>

<style scoped>

li {
  list-style-position: inside;
}
</style>
