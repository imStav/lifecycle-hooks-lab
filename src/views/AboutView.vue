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

const el = ref();
let count = ref(0);

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
  console.log("onUpdated");
});

onBeforeUnmount(() => {
  console.log("onBeforeUnmount");
});

onUnmounted(() => {
  console.log("onUnmounted");
});
</script>

<template>
  <div class="about">
    <h1>This is an about page</h1>
  </div>

  <div ref="el" @click="count++" class="counter">
    {{ count }}
  </div>
</template>

<style scoped>
.counter {
  margin-block: 2rem;
  padding: 1rem 1.5rem;
  border: 1px solid gray;
  border-radius: 8px;
  width: fit-content;
}
</style>
