<script>

export default {
  data() {
    return {
      message: ''
    }
  },

  components: {

  }
}
</script>

<template>
    <div>
        <div>
            <h3>
                {{ project.title }}
            </h3>
            <h4>
                {{ project.description }}
            </h4>
            <h5 v-if="project.type != null">
                {{ project.type.name }}
            </h5>
            <h5 v-else>
                -
            </h5>
            <div class="tech-container" v-for="technology in project.technologies" :key="technology.id">
                {{ technology.name }}
            </div>
            <div>
                {{ project.visible }}
            </div>
        </div>
    </div>
</template>

<style scoped>

</style>
