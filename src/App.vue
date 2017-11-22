<template>
  <div id="app">
    <Teaser />
  </div>
</template>

<script>
import Teaser from './components/Teaser'

export default {
  name: 'app',
  components: {
    Teaser
  }
}
</script>

<style lang="scss">

body {
  background: rgba(25, 10, 15, 1);
  height: 100vh;
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #fff;
}

</style>
