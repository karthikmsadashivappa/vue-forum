<template>
  <div>
    <h1>welcome to vue forum</h1>
    <div v-for="thread in threads">
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
console.log(sourceData);
export default {
  data() {
    return {
      threads: sourceData.threads,
      posts: sourceData.posts,
      users: sourceData.users
    };
  }
};
</script>
