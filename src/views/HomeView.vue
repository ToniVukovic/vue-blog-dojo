<template>
  <div class="home">
    <p ref="p">My name is {{ name }} and I am {{ age }} years old.</p>
    <button @click="handleClick">click me</button>
    <button @click="age++">add 1 to age</button>
    <input type="text" v-model="name" />
  </div>
</template>

<script>
import { ref } from "vue";

// @ is an alias to /src

export default {
  name: "HomeView",
  setup() {
    // const p = ref(null);
    const name = ref("mario");
    const age = ref(30);
    const handleClick = () => {
      name.value = "Luigi";
      age.value = 29;
    };

    return { name, age, handleClick };
  },
};
</script>
