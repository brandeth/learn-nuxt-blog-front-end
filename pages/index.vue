<script setup lang="ts">
// Create an interface for Post
interface Post {
  id: number;
  title: string;
  body: string;
  created_at: string;
  updated_at: string;
  user: {
    id: number;
    name: string;
  };
}

// Fetch posts using nuxt useFetch with interface Post from localhost:8000/api/posts
const { data: posts } = useFetch<Post[]>("http://localhost:8000/api/posts");
</script>

<template>
  <div class="container mx-auto w-1/2 py-8 divide-y space-y-8 divide-gray-300">
    <PostItem v-for="post in posts" :key="post.id" :post="post" />
  </div>
</template>
