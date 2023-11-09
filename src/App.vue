<template>
  <CounterComponents />
</template>

<script>
import CounterComponents from './components/CounterComponents.vue'

export default {
  name: 'App',
  components: {
    CounterComponents
  }
}
</script>

<style>
#app {
  text-align: center;
}
</style>
