<template>
  <div class="games">
    <nav class="navbar bg-dark" data-bs-theme="dark">
      <div class="container-fluid justify-content-center">
        <span class="navbar-brand mb-0 h1">{{title}}</span>
      </div>
    </nav>

    <div class="alert alert-success my-5" role="alert">
      <h4 class="alert-heading">¡Bienvenido!</h4>
      <hr>
      <p class="mb-0">A continuación encontrarás la lista de los juegos que prefieres</p>
    </div>

    <table class="table table-dark text-center align-middle w-75 m-auto">
      <thead>
        <tr>
          <th scope="col">#</th>
          <th scope="col">Juego</th>
          <th scope="col">Eliminar juego de la lista</th>
        </tr>
      </thead>
      <tbody v-for="(game, index) in gameList" :key="game">
        <tr>
          <th scope="row">{{index+1}}</th>
          <td>{{game}}</td>
          <td><button class="btn btn-danger" @click="rmvGame(index)">eliminar</button></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "games-component",
  props:{
    title:{
      type: String,
      default: 'Mi titulo por default'
    },
    gameList:{
      type: Array,
      required: true,
    },
  },
  methods:{
    rmvGame(index){
      this.$emit('delete', index)
    }
  }
}
</script>

<style>
.imagenes{
  width: 10rem;
}
</style>