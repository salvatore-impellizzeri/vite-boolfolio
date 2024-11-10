<script>
import axios from 'axios';

export default {
  data() {
    return {
      projects: [],
    }
  },

  mounted(){
    this.getProjects();
  },

  methods:{
    getProjects(){
        axios
            .get('http://127.0.0.1:8000/api/projects')
            .then((res) => {
                this.projects = res.data.projects.data;
            });
    }
  }
}
</script>

<template> 
  <div>
    <div class="container">
      <div class="projects-container">
        <div v-for="project in projects" :key="project.id" class="single-project">
          <h3>
            {{ project.title }}
          </h3>
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
            <router-link class="fs-6" :to="{ name: 'projects-show', params: { slug: project.slug } }">
              Leggi tutto
            </router-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
  .container {
    width: 100%;
    margin: 0 auto;
    padding: 20px;
  }

  .projects-container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    justify-content: space-between;
  }

  .single-project {
    background-color: rgba(211, 211, 211, 0.479);
    border: 1px solid black;
    padding: 20px;
    width: calc(33.33% - 20px); 
    box-sizing: border-box; 
    border-radius: 8px; 
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); 
    transition: transform 0.3s ease; 
  }

  .single-project:hover {
    transform: translateY(-5px); 
  }

  .single-project h3 {
    font-size: 20px;
    font-weight: bold;
    margin-bottom: 10px;
  }

  .single-project h5 {
    font-size: 15px;
    color: #555;
  }

  .tech-container {
    background-color: #e7e7e7;
    border-radius: 4px;
    font-size: 13px;
    display: inline-block;
  }

</style>
