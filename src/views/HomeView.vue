<script setup>
import {
  onBeforeMount,
  onMounted,
  onBeforeUpdate,
  onUpdated,
  onBeforeUnmount,
  onUnmounted,
  ref,
} from "vue";

import { useCounterStore } from "../stores/counter";

const pageTitle = ref("Lifecycle Hooks Lab");
const el = ref();
const store = useCounterStore();

onBeforeMount(() => {
  console.log("onBeforeMount");
});

onMounted(() => {
  console.log("onMounted", el.value);
});

onBeforeUpdate(() => {
  console.log("onBeforeUpdate");
});

onUpdated(() => {
  console.log("onUpdated", el.value);
});

onBeforeUnmount(() => {
  console.log("onBeforeUnmount");
});

onUnmounted(() => {
  console.log("onUnmounted", el.value);
});
</script>

<template>
  <main>
    <div class="about">
      <h1>{{ pageTitle }}</h1>
      <p>See the behavior of hooks, and how they affect the rendering</p>
    </div>

    <div class="instructions">
      <p>Open the console</p>
    </div>

    <div ref="el" @click="store.increment" class="counter">
      {{ store.count }}
    </div>
  </main>
</template>

<style scoped>
main {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: calc(100vh - 8rem);
}
.about {
  margin: 0 auto;
  width: fit-content;
  text-align: center;
}

.instructions {
  width: fit-content;
  margin: 30px auto;
  filter: opacity(0.8);
  font-style: italic;
}

.counter {
  margin: 2rem auto;
  padding: 1rem 1.5rem;
  border: 1px solid cornflowerblue;
  border-radius: 8px;
  width: fit-content;
  cursor: pointer;
  transition: all ease-in-out 0.3s;
  box-shadow: 5px 5px cornflowerblue;
}

.counter:hover {
  box-shadow: 3px 3px cornflowerblue;
}
</style>
