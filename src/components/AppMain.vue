<script>
import ProjectCard from './ProjectCard.vue';

export default {
  data() {
    return {
      message: ''
    }
  },

  components: {
    ProjectCard,
  }
}
</script>

<!-- All'interno del template ci va un solo figlio -->
<template>
  <div>
    <router-view></router-view>
  </div>
</template>

<style scoped>

</style>
