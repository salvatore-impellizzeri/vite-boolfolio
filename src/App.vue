<script>
import AppMain from './components/AppMain.vue';

export default {
  data() {
    return {

    }
  },

  components: {
    AppMain,
  }
}
</script>

<template> 
  <header>
    <h1> 
        <AppMain />
    </h1>
  </header>
</template>

<style lang="scss" scoped>
@use 'assets/scss/main.scss' as *;

</style>

