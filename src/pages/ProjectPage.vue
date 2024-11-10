<script>
import axios from 'axios';

export default {
  data() {
    return {
      project: null,
    }
  },

  mounted(){
    this.getProject();
  },

  methods:{
    getProject(){
        axios
            .get('http://127.0.0.1:8000/api/projects' + '/' + this.$route.params.slug)
            .then((res) => {
                this.project = res.data.project;
            })
            .catch((err) => {
                this.$router.push({ name: 'not-found' });
			});
    }
  }
}
</script>

<template>
    <div>
        <div v-if="project != null" class="text-center">
            <h1>
                {{ project.title }}
            </h1>
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
                {{ project.visible === 1 ? 'Pubblicato' : 'Non pubblicato' }}
            </div>
        </div>
    </div>
</template>

<style scoped>

</style>
