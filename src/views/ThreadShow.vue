<template>
  <div>
    <div>
      <h2>{{thread.title}}</h2>
      <div v-for="postId in thread.posts" class="thread-container">
        <h3 class="userName">{{users[posts[postId].userId].name}}</h3>
        <p class="post">{{posts[postId].text}}</p>
      </div>
    </div>
  </div>
</template>

<script>
import sourceData from "@/data";
export default {
  props: {
    id: {
      required: true,
      type: String
    }
  },
  data() {
    return {
      thread: sourceData.threads[this.id],
      posts: sourceData.posts,
      users: sourceData.users
    };
  }
};
</script>
