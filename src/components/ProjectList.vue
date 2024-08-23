<script>
import ProjectCard from './ProjectCard.vue';
import SingleProject from './ProjectCard.vue';
import axios from 'axios';

export default {
    components: {
        ProjectCard,
    },
    data() {
        return {
            projects: [],
        }
    },
    methods:{
        getProjects(){
            axios.get('http://127.0.0.1:8000/api/projects', {
                params: {
                }
            })
            .then((response) => {
                console.log(response.data.results.data);
                this.projects = response.data.results.data;
            })
            .catch(function(error) {
                console.log(error);
            });
        }
    },
    created(){
        this.getProjects();
    }
}
</script>

<template>
    <div class="project-container">
        <ProjectCard v-for="(project,index) in projects" :key="index" :image="project.image" :title="project.title" :author="project.author" :date="project.date" :preview="project.preview" :type="project.type"/>
    </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;

.project-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    gap: 20px;
    padding: 20px;
}
</style>