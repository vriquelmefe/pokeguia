<template>
<div>
   <img src="@/assets/imagen-logo.jpg" alt="">
    <h2>PokeGuía</h2>
    <label for="">Nombre  </label>
    <input type="search" v-model="personajes" placeholder="Nombre Pokemon">
    <button @click="getApiPokemon()">Buscar</button>
    <ConexionApi />
</div>
</template>

<script>
import ConexionApi from '@/components/ConexionApi.vue'
export default {
  name: 'PokeInfoSelect',
  components: {
    ConexionApi,
  },
  methods:{}

}
</script>