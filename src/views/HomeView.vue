<template>
  <div class="home">
    <p>Home</p>
    <div v-if="posts.length">
      <PostList :posts="posts" />
    </div>
    <div v-else><Spinner /></div>
  </div>
</template>

<script>
import PostList from "../components/PostList.vue";
import getPosts from "../composables/getPosts";
import Spinner from "@/components/Spinner.vue";
export default {
  name: "HomeView",
  components: { PostList, Spinner },
  setup() {
    const { posts, error, load } = getPosts();

    load();

    return { posts, error };
  },
};
</script>
