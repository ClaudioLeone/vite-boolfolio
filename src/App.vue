<script>
import axios from 'axios';
// import {store} from './store';
import ProjCard from './components/ProjCard.vue';

export default {
    data() {
        return {
            projects: []
        };
    },
    components: {
      ProjCard
    },
    mounted() {
        this.getProjects();
    },
    methods: {
        getProjects() {
            axios.get("http://127.0.0.1:8000/api/projects").then((resp) => {
                this.projects = resp.data.results;
            });
        }
    },
    components: { ProjCard }
}
</script>

<template>
  <div class="container">
    <h2 class="text-center my-3">Lista progetti</h2>
    <div class="row row-cols-4 g-2">
      <div class="col" v-for="project in projects" :key="project.id">
        <ProjCard :project="project"/>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
</style>