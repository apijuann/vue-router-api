<template>
  <Titulo texto="Ruta artículo con parámetros" />
  <h3>Parametros: {{$route.params.id}}</h3>
  <h3>{{articulo.title}}</h3>
  <p>{{articulo.body}}</p>
</template>

<script>
import Titulo from '../components/Titulo'
export default {
    components:{
        Titulo
    },
    data() {
        return {
            articulo: {}
        }
    },
    methods: {
        async consumirArticulo(){
            try {
                const data = await fetch(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`)
                const objeto = await data.json()
                this.articulo = objeto
            } catch (error) {
            console.log(error)
            }
        }
    },
    created(){
        this.consumirArticulo()
    }
}
</script>

<style>

</style>