<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <Titulo texto="This is the home page..." />
  </div>
</template>

<script>
import Titulo from '../components/Titulo'
export default {
  name: 'Home',
  components: {
    Titulo
  }
}
</script>
