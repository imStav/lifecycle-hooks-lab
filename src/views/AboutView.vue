<script setup>
import { ref } from "vue";
import Ressources from "../components/Ressources.vue";
import Socials from "../components/Socials.vue";

const currentTab = ref("Ressources");

const tabs = {
  Ressources,
  Socials
};
</script>

<template>
  <main>
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
}

button {
  border: 1px solid greenyellow;
  background-color: transparent;
  color: gray;
  margin-inline: .5rem;
  border-radius: 4px;
  padding: .5rem 1rem;
  box-shadow: 5px 5px greenyellow;
}

button:hover {
  box-shadow: 3px 3px greenyellow;
  cursor: pointer;
}

.tabs {
  display: flex;
  justify-content: center;
  margin-block: 2rem;
}
</style>