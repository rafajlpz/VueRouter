<template>
  <Titulo texto="Ruta con parametros" />
  <h2>Parámetro: {{$route.params.id}}</h2>
</template>

<script>
import Titulo from "../components/Titulo.vue"
export default {
    components:{
        Titulo
    },
    data() {
      return {
        articulo: {}
      }
    },
    methods:{
      async consumirArticulo(){
        try{
          const data = await fetch(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`)
          const objeto = await data.json()
          console.log(objeto)
        }catch(error){
          console.log(error)
        }
      }
    }
}
</script>

<style>

</style>