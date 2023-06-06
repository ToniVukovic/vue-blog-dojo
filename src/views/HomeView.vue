<template>
  <div class="home">
    <p>Home</p>
    <input type="text" v-model="search" />
    <p>{{ search }}</p>
    <div v-for="name in matchingNames" :key="name">{{ name }}</div>
    <button @click="handleClick">stop watching</button>
  </div>
</template>

<script>
import { computed, ref, watch } from "vue";

export default {
  name: "HomeView",
  setup() {
    const search = ref("");
    const names = ref(["mario", "luigi", "peach", "bowser"]);

    const stopWatching = watch(search, () => {
      console.log("watch function ran");
    });

    const handleClick = () => {
      stopWatching();
    };

    const matchingNames = computed(() => {
      return names.value.filter((name) => name.includes(search.value));
    });

    return { names, search, matchingNames, handleClick };
  },
};
</script>
