<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

export default {
  data() {
    return {

    }
  },

  components: {
    AppMain,
    AppHeader,
  }
}
</script>

<template> 
  <header>
    <h1> 
        <AppHeader />
    </h1>
  </header>
</template>

<style lang="scss">
@import "bootstrap/scss/bootstrap";

</style>

