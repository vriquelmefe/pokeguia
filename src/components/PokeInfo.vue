<template>
<div>
   <img src="@/assets/imagen-logo.jpg" alt="" class="img-fluid">
    <h1 class="font-weight-bold m-5">{{ title }}</h1>
    <label >Nombre:  </label>
    <input v-model="nombre">
    <button @click="buscandoPokemon">Buscar</button>
    <div>
    <h3 class="card-title font-weight-bold my-4">{{personajes.name}}</h3>
    <img :src="imagen">
    <div class="card container my-5 p-0" style="width: 50%;">
      <div class="card-body">
        <h5 class="card-title font-weight-bold text-dark">Movimientos</h5>
        <p v-for="(movimiento, index) in movimientos" :key="index" class="card-text">{{movimiento.move.name}}</p>
      </div>
      <div class="card-body">
        <h5 class="card-title font-weight-bold text-dark">Habilidades</h5>
        <p v-for="(habilidad, index) in habilidades" :key="index" class="card-text">{{habilidad.ability.name}}</p>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'PokeInfo',
  props: {
    title: String
  },
  data: () => ({
     nombre:"",
     personajes: null,
  }),
  methods:{
    async buscandoPokemon(){
      if(this.nombre !== ""){
         this.getApiPokemon(this.nombre)
      }
    },
    async getApiPokemon(nombre){
      try{
        let response = await fetch(`https://pokeapi.co/api/v2/pokemon/${nombre}`);
        let data = await response.json();
        this.personajes = data;

      } catch (error) {
        alert('Nombre invalido')
        console.log(error)}


      //fetch(`https://pokeapi.co/api/v2/pokemon/${nombre}`);
      // .then(response => response.json())
      // .then(data => {console.log(data.results)
      //   //  console.log(datosPoke.results)
      // })
    },
  },
  computed: {
    imagen(){
      return (
        (this.personajes && this.personajes.sprites && this.personajes.sprites.front_default) || "");
    },
    habilidades(){
      return (this.personajes && this.personajes.abilities) || [];
    },
    movimientos(){
      return (this.personajes && this.personajes.moves) || [];
    }
  },
  created() {
    this.nombre= "pikachu";
    this.buscandoPokemon();
  }

}
</script>

<style>

ul{
  list-style: none;
  margin: 0 auto;
}
</style>