<script setup>
import { ref, onMounted } from "vue";
import { RouterLink } from "vue-router";
import "primeicons/primeicons.css";

const users = ref(null);

// fetch users
const fetchUsers = async () => {
  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/users");
    const data = await response.json();
    users.value = data;
  } catch (error) {
    console.error(error);
  }
};

onMounted(() => {
  fetchUsers();
});
</script>

<template>
  <div v-if="users" class="max-w-5xl mx-auto">
    <h1
      class="text-2xl font-normal capitalize text-green-500 border border-green-500 w-max px-6 rounded-full"
    >
      home
    </h1>

    <table class="table w-full border border-green-500 mt-5">
      <thead>
        <tr
          class="text-center border border-green-500 *:border *:border-green-500 *:py-3 *:capitalize *:text-center"
        >
          <th class="w-[5%]">ID</th>
          <th>name</th>
          <th>city</th>
          <th>username</th>
          <th>phone</th>
          <th class="w-[10%]">action</th>
        </tr>
      </thead>
      <tbody>
        <tr
          class="text-center border border-green-500 *:border *:border-green-500 *:py-2 even:bg-green-950"
          v-for="user in users"
          :key="user.id"
        >
          <td>{{ user.id }}</td>
          <td>{{ user.name }}</td>
          <td>{{ user.address.city }}</td>
          <td>{{ user.username }}</td>
          <td>{{ user.phone }}</td>
          <td>
            <RouterLink
              :to="`/users/${user.id}`"
              class="pi pi-pencil duration-200 hover:text-green-500 mr-6"
              title="edit"
            ></RouterLink>
            <RouterLink
              to="/"
              title="delete"
              class="pi pi-trash duration-200 hover:text-green-500"
            ></RouterLink>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
  <div class="text-left max-w-5xl mx-auto" v-else>Loading...</div>
</template>
