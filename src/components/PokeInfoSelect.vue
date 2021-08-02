<template>
  <div>
    <img src="" alt="">
    <h2>Movimientos</h2>
      <ul>
        <li>{{movimientosLista}}</li>
      </ul>
    <h2>Habilidades</h2>
    <ul>
        <li>{{habilidadesLista}}</li>
      </ul>
  </div>
</template>

<script>
export default {
  name : 'PokeInfoSelect',
  data: () => ({
     personajes: [
      {
      nombre: '',
      imagen: '',
      movimientos: [],
      habilidades : [],
    }
    ],
      personaje : '',
  }),
  props: {
    movimientosLista : {
      type: Array,
    },
    habilidadesLista : {
      type: Array,
    },
  }
}
</script>

<style>
 ul{
   list-style: none;
   align-content: center;
 }
</style>