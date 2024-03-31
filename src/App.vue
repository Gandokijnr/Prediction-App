<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header class="sticky top-0">

    <div class="wrapper flex justify-between bg-blue-950 p-8 text-white flex-wrap">
      <div class="nav-logo">
        <router-link to="/" class="text-2xl">
            2Sure
        </router-link>
      </div>
      <nav class="flex gap-5">
        <RouterLink to="/">Tips store</RouterLink>
        <RouterLink to="/about">Rollover</RouterLink>
        <RouterLink to="/about">50 Odds</RouterLink>
        <RouterLink to="/about">10 Odds</RouterLink>
        <RouterLink to="/about">5 Odds</RouterLink>
        <RouterLink to="/about">2 Odds</RouterLink>
      </nav>
      <div class="nav-button flex gap-5">
        <router-link to="/login">Login</router-link>
        <router-link to="/register">Register</router-link>
      </div>
    </div>
  </header>

  <RouterView />
</template>