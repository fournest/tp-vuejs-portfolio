<script setup>
const props = defineProps(['project']);


</script>

<template>



    <div class="projects-grid">
        <!-- <div v-for="project in projects" :key="project.id" class="project-card"> -->

        <div class="card-content">
            <h3>{{ project.title }}</h3>
            <p>{{ project.description }}</p>
            <img v-if="project.img" :src="project.img">

        </div>
        <!-- </div> -->
    </div>

</template>

<style scoped></style>