<script setup>
import Navigation from './components/Navigation.vue';

import { shallowRef } from 'vue'
import Home from './components/Home.vue';

let currentView = shallowRef(Home);
const handleNavigation = (viewName) => {

  currentView.value = viewName;
  

}

</script>

<template>


  <main>

    <Navigation @nav="handleNavigation" />
    <!-- <transition name="fade" mode="out-in"> -->
    <component :is='currentView'></component>

    <!-- </transition> -->


  </main>

</template>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

main {

  text-align: center;
  padding: 20px;
  font-family: sans-serif;
  color: #333;
  width: 150vh;
  min-height: 1200px;
  margin: 20px auto;
  background-image: url('https://cdn.pixabay.com/photo/2020/08/25/18/29/workplace-5517762_1280.jpg');
  background-size: cover;
  background-repeat: no-repeat;


}

h2 {
  text-align: center;
  margin-bottom: 20px;
  color: rgb(170, 20, 20);
}

nav {
  display: flex;
  justify-content: space-around;
  padding: 10px;
  background-color: #91dcdc;
  border-radius: 5px;
}

button {
  padding: 8px 15px;
  border:2px solid lightgoldenrodyellow;
  border-radius: 8px;
  background-color: #007bff;
  color: white;
  cursor: pointer;
  font-size: 1em;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #0056b3;
  transform: translateY(-2px);
}

form {
  display: flex;
  flex-direction: column;
  gap: 15px;

  max-width: 500px;
  margin: 20px auto;

  padding: 25px;
  border: 1px solid #ddd;
  border-radius: 8px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  background-color: #ffffff6c;
}



label {
  font-weight: bold;
  color: #555;
  margin-bottom: 5px;
}

input[type="text"],
input[type="email"],
input[type="tel"],
textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 5px;
  font-size: 1em;
  box-sizing: border-box;
  transition: border-color 0.3s ease;
}

input[type="text"]:focus,
input[type="email"]:focus,
input[type="tel"]:focus,
textarea:focus {
  border-color: #007bff;
  outline: none;
}

textarea {
  resize: vertical;
  min-height: 120px;
}

.checkbox-container {
  display: flex;
  align-items: flex-start;
  gap: 10px;
}

.checkbox-container input[type="checkbox"] {
  margin-top: 5px;
}

.checkbox-container label {
  font-weight: normal;
  color: #666;
  margin-bottom: 0;
  font-size: 0.9em;
}

.discribe {
  font-family: Arial, sans-serif;
  line-height: 2;
  color: #333;
  padding: 20px;
  background-color: #f9f9f93a;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.274);
  max-width: 800px;
  margin: 20px auto;
}

.discribe p {
  margin-bottom: 1em;
  border-radius: 15px;
}


.discribe p:first-of-type {
  font-weight: bold;
  color: #0056b3;
}


.discribe p:nth-of-type(2),
.discribe p:nth-of-type(3) {
  font-size: 0.95em;
  color: #007bff;
}



.discribe strong {
  color: #007bff;
}

img {
  width: 160px;
  height: 160px;
  border-radius: 50%;
  object-fit:cover;
  margin-bottom: 20px;
}

h1 {
  font-size: 2.2em;
  color: #007bff;
  margin-bottom: 15px;
}

p {
  font-size: 1em;
  max-width: 600px;
  margin: 0 auto;
  color: mediumorchid;
}

.filter {
  color: blanchedalmond;
}

.progress-bar-container {
  width: 100%;
  height: 20px;
  background-color: #e0e0e0;
  border-radius: 10px;
  overflow: hidden;
  padding: 50px;
}

.skills {
  height: 100%;
  background-color: rgb(214, 11, 34);
  border-radius: 10px;
  transition: width 0.5s ease-in-out;
  padding: 15px;
  display: flex;
  justify-content: center;
  align-items: center;

}

.html {

  width: 60%;
  background-color: #007bff;

}

.css {
  width: 60%;
  background-color: lightsalmon;
}

.js {

  width: 50%;
  background-color: rgb(80, 192, 80);
}

.bootstrap {

  width: 25%;
  background-color: lightseagreen;
}

.vue-js {
  width: 60%;
  background-color: lightcoral;
}

.card-content {
  padding: 10px;
  margin: 10px;
  background-color: rgba(21, 140, 142, 0.604);
  border-radius: 10px;
  box-shadow:0 4px 12px #851616a2;
}

h3 {
  
  font-size: 20px;
  color: rgba(137, 43, 226, 0.523);
}

.projects-section {
  padding: 30px 20px;
  background-color: #f9f9f934;
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.262);
  margin: 20px auto;
  max-width: 1200px;
}

.filter {
  text-align: center;
  margin-bottom: 40px;
  padding: 20px;
  background-color: #ffffff64;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.03);
}

.filter h2 {
  color: #333;
  font-size: 2.5em;
  margin-bottom: 15px;
  font-weight: 700;
}

.filter label {
  display: block;
  margin-bottom: 10px;
  font-size: 1.1em;
  color: #555;
  font-weight: 500;
}

.filter input[type="text"] {
  width: 100%;
  max-width: 400px;
  padding: 12px 15px;
  border: 1px solid #ddd;
  border-radius: 6px;
  font-size: 1em;
  color: #333;
  transition: all 0.3s ease;
  box-shadow: inset 0 1px 3px rgba(0, 0, 0, 0.05);
}

.filter input[type="text"]:focus {
  border-color: #007bff;
  box-shadow: 0 0 0 3px rgba(0, 123, 255, 0.25);
  outline: none;
}


.filters {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 15px;
  margin-bottom: 40px;
}

.filters button {
  background-color: #e2e6ea;
  color: #495057;
  border: none;
  padding: 12px 25px;
  border-radius: 25px;
  font-size: 1em;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  font-weight: 600;
}

.filters button:hover {
  background-color: #d3d9df;
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
}

.filters button.active {
  background-color: #007bff;
  color: #ffffff;
  box-shadow: 0 4px 8px rgba(0, 123, 255, 0.3);
  transform: scale(1.05);
}

/* .fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
} */
</style>
