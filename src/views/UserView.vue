<script setup>
import { ref, onMounted } from "vue";
import { useRoute } from "vue-router";
import Header from "@/components/Header.vue";

const currentUser = ref(null);
const route = useRoute();

// fetch users
const fetchCurrentUser = async () => {
  try {
    const response = await fetch(
      `https://jsonplaceholder.typicode.com/users/${route.params.id}`
    );
    const data = await response.json();
    currentUser.value = data;
  } catch (error) {
    console.error(error);
  }
};

onMounted(() => {
  fetchCurrentUser();
});
</script>

<template>
  <Header />
  <p v-if="!currentUser" class="max-w-5xl mx-auto text-left">Loading...</p>
  <main v-else class="max-w-5xl mx-auto">
    <h2 class="text-2xl">
      ID : <span class="text-green-500">{{ currentUser.id }}</span>
    </h2>
    <h2 class="text-2xl">
      Name : <span class="text-green-500">{{ currentUser.name }}</span>
    </h2>
    <h2 class="text-2xl">
      City : <span class="text-green-500">{{ currentUser.address.city }}</span>
    </h2>
    <h2 class="text-2xl">
      Username : <span class="text-green-500">{{ currentUser.username }}</span>
    </h2>
    <h2 class="text-2xl">
      Phone : <span class="text-green-500">{{ currentUser.phone }}</span>
    </h2>
    <h2 class="text-2xl">
      Catch Phrase :
      <span class="text-green-500">{{ currentUser.company.catchPhrase }}</span>
    </h2>
    <p class="indent-8 font-extralight text-lg mt-6 text-justify">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Veritatis, esse
      voluptas, totam fugiat alias error quas minima porro obcaecati magni odio
      aliquid illo quia culpa ullam. Quos nobis cum itaque rerum omnis minus.
      Earum natus non incidunt atque facere repellendus aut repellat eos
      commodi. Voluptates a facilis aliquid quae, obcaecati inventore ab
      recusandae minima ut veniam natus porro autem magnam odio quod tempore
      consequatur esse veritatis? Dolor culpa, blanditiis ea tenetur nostrum
      perferendis, debitis rerum molestias explicabo repellendus aliquid? Non
      debitis eveniet harum cum id inventore itaque sequi in explicabo. Possimus
      assumenda cum nulla reiciendis, saepe ratione facilis iure ipsa molestiae.
      Itaque sint inventore excepturi repudiandae, iure tempora, ullam
      asperiores aut aspernatur ad cum minus iste obcaecati temporibus
      architecto, at eligendi corporis veritatis suscipit minima repellendus.
      Sequi, numquam sit, perspiciatis in ad ducimus ut blanditiis adipisci,
      doloribus eligendi harum mollitia. Nisi quia temporibus minus id enim?
      Tempore maxime id dolorem molestias dicta, necessitatibus perferendis quas
      doloribus ad nisi rerum perspiciatis quae est incidunt unde, nemo quia
      magni autem quam animi quidem! Neque expedita ex nihil nam vel dignissimos
      laboriosam, blanditiis a repudiandae eum dolorum, quasi error eveniet sint
      inventore molestiae quo rem laudantium. Id, explicabo nobis! Nostrum
      labore fugit eaque?
    </p>
  </main>
</template>
