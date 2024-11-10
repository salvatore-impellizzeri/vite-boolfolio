<script>
import ProjectCard from '../components/ProjectCard.vue';

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
    <div>
        <h1 class="text-center fw-bold">
            Projects
        </h1>
    </div>
    <ProjectCard />
  </div>
</template>

<style scoped>

</style>
