<script setup>
import { ref, computed, reactive } from 'vue';
import ProjectCard from '../components/ProjectCard.vue';


const projects = reactive([
    {
        id: 1, title: "tp patachou", categorie: "html/css",
        description: "tp consistant à faire une page web responsive en html/css à partir d'une maquette.", img: "./src/assets/img/poche-douille_histoire-patachou.png"

    },
    {
        id: 2, title: "tp périgord", categorie: "html/css",
        description: "tp consistant à faire une page en html/css à partir de consignes données.", img: "./src/assets/img/perirgordnoir3.jpeg"
    },
    {
        id: 3, title: "tp maison du chocolat", categorie: "html/css",
        description: "tp consistant à faire une page web en html/css à partir d'une maquette.", img: "./src/assets/img/article-image-2.jpg"
    },
    {
        id: 4, title: "tp validation formulaire", categorie: "Javascript",
        description: "tp consistant à créer un formulaire en Javascript à partir de consignes données.", img: "./src/assets/img/tp-validation-formulaire.png"
    },
    {
        id: 5, title: "tp xylophone", categorie: "Javascript",
        description: "tp consistant à faire une page web en Javasript principalement à partir de consignes données.", img: "./src/assets/img/tp-xylophone-interactif.png"
    },
    {
        id: 6, title: "tp computed-properties, watchers et reactive", categorie: "Javascript",
        description: "tp consistant à faire une page web en Javascript (vue.js) à partir de consignes données.", img: "./src/assets/img/tp-exercices-computed-properties.png"
    }
]);

const currentCategory = ref('Tout')
const searchTerm = ref('');

const uniqueCategories = computed(() => {
    const categories = new Set(projects.map(project => project.categorie))
    return ['Tout', ...Array.from(categories)];
});

const filteredProjects = computed(() => {
    let filtered = projects;


    if (currentCategory.value !== 'Tout') {
        filtered = filtered.filter(project => project.categorie === currentCategory.value);
    }

    if (searchTerm.value) {
        const lowerCaseSearchTerm = searchTerm.value.toLowerCase();
        filtered = filtered.filter(project => project.title.toLowerCase().includes(lowerCaseSearchTerm));
    }
    return filtered;
});

const filterProjects = (category) => {
    currentCategory.value = category;
};

</script>

<template>
    <div class="filter">
        <h2>Mes projets</h2>
        <label for="eventFilter">Filtrer par titre</label>
        <input type="text" id="eventFilter" v-model="searchTerm" placeholder="Saisissez une partie du texte">
    </div>

    <div class="projects-section">
        <div class="filters">
            <button v-for="category in uniqueCategories" :key="category" @click="filterProjects(category)"
                :class="{ active: currentCategory === category }"> {{ category }}</button>
        </div>

        <div class="projects-list">
            <ProjectCard v-for="project in filteredProjects" :key="project.id" :project="project" />

        </div>
    </div>

</template>

<style scoped></style>