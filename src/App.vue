<template>
  <FormContainer />
</template>

<script>
import FormContainer from './components/FormContainer.vue'

export default {
  name: 'App',
  components: {
    FormContainer
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: linear-gradient(45deg, #EECFBA, #C5DDE8);
}
</style>
