<template>
  <div id="app">
    <h1>Crea una nueva tarea</h1>

    <label>Tarea </label>
    <input v-model="tarea" placeholder="Ingresa una nueva tarea">
    <button @click="agregarTareas">Crear</button>

    <h2>Lista</h2>
    <ul class="list">
      <li v-for="(tarea, $index) in arregloTareas" :key="$index">
        {{$index + 1}}: {{tarea}}
      </li>
    </ul>
  </div>
</template>

<script>

export default {
  name: 'App',
  data: () => ({
    tarea: "",
    arregloTareas: [],
  }),

  methods: {
    agregarTareas: function(){
      this.arregloTareas.push(this.tarea)
      this.tarea = ""
    }
  },
};
</script>

<style lang="scss" scoped>
  #app {
    font-family: Arial, Helvetica, sans-serif;
    text-align: center;
  }

  .list {
    text-align: center;
    list-style-position: inside;
    padding: 0;
  }
</style>
