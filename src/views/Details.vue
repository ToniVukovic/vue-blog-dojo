<template>
  <!-- <div v-if="error">{{ error }}</div> -->
  <div v-if="post" class="post">
    <h2>{{ post.title }}</h2>
    <p>{{ post.body }}</p>
  </div>
  <div v-else>
    <Spinner />
  </div>
</template>

<script>
import getPost from "@/composables/getPost";
import Spinner from "@/components/Spinner.vue";
export default {
  props: ["id"],
  components: { Spinner },
  setup(props) {
    const { post, error, load } = getPost(props.id);
    load();
    return { post, error };
  },
};
</script>

<style scoped>
.post {
  background: #ddd;
}
</style>
