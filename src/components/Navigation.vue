<script setup>



import AboutSection from './AboutSection.vue';

import ProjectList from './ProjectList.vue';
import SkillBadge from './SkillBadge.vue';
import ContactForm from './ContactForm.vue';
import Home from './Home.vue';




</script>

<template>
 
 

<div id="home">
    <br>
    <nav>
      <button @click="$emit('nav', Home)">Accueil</button>
      <button @click="$emit('nav', AboutSection)">À propos</button>
      <button @click="$emit('nav', ProjectList)">Projets</button>
      
      <button @click="$emit('nav', SkillBadge)">Compétences</button>
      <button @click="$emit('nav', ContactForm)">Contact</button>
    </nav>
    <br>
   
  </div>
</template>


<style scoped>


</style>