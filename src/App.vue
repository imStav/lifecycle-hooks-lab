<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <div class="wrapper">
    <nav>
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/about">About</RouterLink>
    </nav>
  </div>

  <router-view v-slot="{ Component }">
    <transition name="nav">
      <component :is="Component" />
    </transition>
  </router-view>
</template>

<style scoped>
nav a {
  margin-inline: 1rem;
  color: cornflowerblue;
  font-weight: bold;
  letter-spacing: .1rem;
  text-decoration: none;
}

.wrapper {
  display: flex;
  justify-content: center;
}

.nav-enter-from,
.nav-leave-to {
  filter: opacity(0);
}
.nav-enter-active,
.nav-leave-active {
  transition: all 0.3s ease-in-out;
}
</style>
