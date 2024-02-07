<script setup>
import { ref } from "vue";
const data = ref({});

function create() {
  console.log(data.value);
}
</script>

<template>
  <div class="max-w-5xl mx-auto">
    <h1
      class="text-2xl font-normal capitalize text-green-500 border border-green-500 w-max px-6 rounded-full"
    >
      create
    </h1>
    <form
      @submit.prevent="create"
      class="border border-green-500 p-6 mt-4 rounded-lg *:flex *:flex-col *:gap-2 flex flex-col gap-4 w-2/4"
    >
      <div>
        <label for="name">Name</label>
        <input
          class="px-4 py-1 rounded-sm bg-green-950 focus:ring-green-500 focus:ring-1 focus:outline-none"
          type="text"
          name="name"
          id="name"
          v-model="data.name"
          required
          placeholder="Enter name..."
        />
      </div>
      <div>
        <label for="city">City</label>
        <input
          class="px-4 py-1 rounded-sm bg-green-950 focus:ring-green-500 focus:ring-1 focus:outline-none"
          type="text"
          name="city"
          id="city"
          v-model="data.city"
          required
          placeholder="Enter city..."
        />
      </div>
      <div>
        <label for="username">Username</label>
        <input
          class="px-4 py-1 rounded-sm bg-green-950 focus:ring-green-500 focus:ring-1 focus:outline-none"
          type="text"
          name="username"
          id="username"
          v-model="data.username"
          required
          placeholder="Enter username..."
        />
      </div>
      <div>
        <label for="phone">Phone</label>
        <input
          class="px-4 py-1 rounded-sm bg-green-950 focus:ring-green-500 focus:ring-1 focus:outline-none"
          type="text"
          name="phone"
          id="phone"
          v-model="data.phone"
          required
          placeholder="Enter phone..."
        />
      </div>
      <button
        class="bg-green-500 py-2 px-4 items-center rounded-lg duration-200 hover:bg-green-700"
        type="submit"
      >
        Submit
      </button>
    </form>
  </div>
</template>
