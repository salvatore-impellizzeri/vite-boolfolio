<script>
import ProjectCard from './ProjectCard.vue';

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
    <nav class="navbar navbar-expand-lg bg-body-tertiary">
        <div class="container-fluid">
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav">
                    <li class="nav-item">
                        <router-link :to="{ name: 'home'}" class="nav-link active">
                            Home
                        </router-link>
                    </li>
                    <li class="nav-item">
                        <router-link :to="{ name: 'about'}" class="nav-link">
                            About
                        </router-link>
                    </li>
                    <li class="nav-item">
                        <router-link :to="{ name: 'projects-index'}" class="nav-link">
                            Projects
                        </router-link>
                    </li>
                    <!-- <li class="nav-item">
                        <router-link :to="{ name: 'projects-show'}" class="nav-link">
                            
                        </router-link>
                    </li> -->
                </ul>
            </div>
        </div>
    </nav>
  </div>
</template>

<style scoped>
.nav-link{
    font-size: 20px;
}
</style>
