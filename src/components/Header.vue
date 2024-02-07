<script setup>
import { RouterLink } from "vue-router";
</script>

<template>
  <header class="border-b-2 border-green-500 sticky z-50 mb-6">
    <nav class="max-w-5xl mx-auto py-4 flex items-center justify-between">
      <RouterLink
        to="/"
        class="no-underline text-3xl uppercase font-bold duration-200 hover:text-green-500"
        >monos</RouterLink
      >
      <ul class="flex items-center gap-6">
        <li>
          <RouterLink
            to="/"
            class="capitalize text-lg no-underline hover:text-green-500 duration-200 [&.active]:text-green-500"
            >home</RouterLink
          >
        </li>
        <li>
          <RouterLink
            to="/about"
            class="capitalize text-lg no-underline hover:text-green-500 duration-200 [&.active]:text-green-500"
            >about</RouterLink
          >
        </li>
        <li>
          <RouterLink
            to="/create"
            class="capitalize text-lg no-underline hover:text-green-500 duration-200 [&.active]:text-green-500"
            >create</RouterLink
          >
        </li>
      </ul>
    </nav>
  </header>
</template>
