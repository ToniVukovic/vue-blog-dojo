<template>
  <div class="home">
    <p>Home</p>
    <div v-if="toggleShow">
      <PostList :posts="posts" />
    </div>
    <button @click="toggleShow = !toggleShow">Show posts</button>
    <button @click="posts.pop()">delete post</button>
  </div>
</template>

<script>
import PostList from "../components/PostList.vue";
import { ref } from "vue";

export default {
  name: "HomeView",
  components: { PostList },
  setup() {
    const posts = ref([
      {
        title: "welcome to the blog",
        body: "lorem ipsum Lorem ipsum dolor, sit amet consectetur adipisicing elit. Facere officia, molestiae laborum voluptates odit minima quisquam ex, culpa consequuntur architecto id reprehenderit. Itaque eaque ex laboriosam accusamus temporibus sit praesentium omnis facere? Labore iure at delectus suscipit magni incidunt architecto eum sequi voluptates! Omnis atque, dicta recusandae ab molestiae quidem!",
        id: 1,
      },
      { title: "top 5 css tips", body: "lorem ipsum", id: 2 },
    ]);

    const toggleShow = ref(true);

    return { posts, toggleShow };
  },
};
</script>
