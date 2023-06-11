<template>
  <div class="home">
    <p>Home</p>
    <div v-if="posts.length">
      <PostList :posts="posts" />
    </div>
    <div v-else>Loading...</div>
  </div>
</template>

<script>
import PostList from "../components/PostList.vue";
import { ref } from "vue";

export default {
  name: "HomeView",
  components: { PostList },
  setup() {
    const posts = ref([]);
    const error = ref(null);

    const load = async () => {
      try {
        let data = await fetch("http://localhost:3000/posts");
        if (!data.ok) {
          throw Error("data is not ok");
        }
        posts.value = await data.json();
      } catch (err) {
        error.value = err.message;
        console.log(err.message);
      }
    };

    load();

    return { posts };
  },
};
</script>
