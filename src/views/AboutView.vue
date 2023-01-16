<script setup>
import { ref } from "vue";
import Ressources from "../components/Ressources.vue";
import Socials from "../components/Socials.vue";

const pageTitle = ref("About");
const currentTab = ref("Ressources");

const tabs = {
  Ressources,
  Socials
};
</script>

<template>
  <main>
    <div class="about">
      <h1>{{ pageTitle }}</h1>
      <p>Lifecycle Hooks Lab</p>
      
      <blockquote>
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quibusdam, vitae!
      </blockquote>
    </div>

    <div class="tabs">
      <button v-for="(_, tab) in tabs" @click="currentTab = tab" class="" variant="light">
        {{ tab }}
      </button>
    </div>

    <KeepAlive>
      <component :is="tabs[currentTab]" class="tab"></component>
    </KeepAlive>
  </main>
</template>

<style>
main {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-block: 2rem;
}

button {
  border: 1px solid cornflowerblue;
  background-color: transparent;
  color: #ccd7ea;
  margin-inline: .5rem;
  border-radius: 4px;
  padding: .5rem 1rem;
  transition: all ease-in-out 0.3s;
  box-shadow: 5px 5px cornflowerblue;
}

button:hover {
  box-shadow: 3px 3px cornflowerblue;
  cursor: pointer;
}

.about {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.about blockquote {
  margin-top: 1rem;
  font-style: italic;
}

.tabs {
  display: flex;
  justify-content: center;
  margin-block: 2rem;
}
</style>