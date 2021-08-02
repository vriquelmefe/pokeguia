<template>
  <div>
    <img src="" alt="">
    <h2>Movimientos</h2>
      <p >{{movimientosLista}}</p>
    <h2>Habilidades</h2>
      <p  >{{habilidadesLista}}</p>     
  </div>
</template>

<script>
export default {
  name : 'PokeInfoSelect',
 
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