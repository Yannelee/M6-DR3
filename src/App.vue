<template>
  <div id="app">
    <Games 
      title="Tienda Bit-Game" 
      :gameList="games"
      @delete='rmvGame'
      >
    </Games>
  </div>
</template>

<script>
import Games from '@/components/Games.vue'

export default {
  name: 'App',
  components: {
    Games
  },
  data: function(){
    return{
      games: [
        "Arena of valor", 
        "Pokemon Unite", 
        "Donkey Kong", 
        "Heroes of the storm", 
        "Valorant"
      ]
    }
  },
  methods:{
    rmvGame(index){
      this.games.splice(index,1)
    }
  }
}
</script>

<style>

</style>
