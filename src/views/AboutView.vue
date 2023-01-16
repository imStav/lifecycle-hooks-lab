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
      <div>
        <h1>{{ pageTitle }}</h1>
        <p>Lifecycle Hooks Lab</p>
      
        <blockquote>
          Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quibusdam, vitae!
        </blockquote>
      </div>

      <div class="cube"></div>
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

<style scoped>
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
  box-shadow: -5px 5px cornflowerblue;
}

button:hover {
  box-shadow: -3px 3px cornflowerblue;
  cursor: pointer;
}

/* .about {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
} */

/* .about blockquote {
  margin-top: 1rem;
  font-style: italic;
  text-align: center;
} */

/* .cube {
  width: 100px;
  height: 100px;
  border-radius: 6px;
  background-color: cornflowerblue;
  box-shadow: -10px 10px blueviolet;
} */

.tabs {
  display: flex;
  justify-content: center;
  margin-block: 2rem;
}
</style>