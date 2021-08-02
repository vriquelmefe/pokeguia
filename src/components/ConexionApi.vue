<template>
  <PokeInfoSelect/>
</template>

<script>
import PokeInfoSelect from '@/components/PokeInfoSelect.vue';
export default {
  name: 'conexion-api',
  components: {
    PokeInfoSelect
  },
  data:  () => ({}),
  methods:{
    getApiPokemon(nombrePokemon){
      fetch(`https://pokeapi.co/api/v2/pokemon/${nombrePokemon}`)
      .then(response => response.json())
      .then(data => {console.log(data.results)
        //  const datosPoke = data.results.url.filter(poke => poke.name === nombrePokemon);
        //  console.log(datosPoke.results)
      })
      .catch((error) => console.log(error))
    },
    buscandoPokemon(){
      this.personajes.push({
        nombre: this.personajes.name, 
        imagen: this.sprites.front_default,
        movimientos : this.movimientos
      })
    }
  },
  computed: {
    // mounted(){
    //   return {
    //     personaje = 'pikachu',
    //     fetchApiPokemon()
    //   } 
    // },
  },
  created() {
    this.getApiPokemon();
  },

}
</script>