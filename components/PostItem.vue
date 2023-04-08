<script lang="ts" setup>
// define props and assign to const props
const props = defineProps<{
  post: {
    id: number;
    title: string;
    body: string;
    created_at: string;
    updated_at: string;
    user: {
      id: number;
      name: string;
    };
  };
}>();
</script>

<template>
  <div class="post-container py-8">
    <h3 class="text-3xl font-bold">
      <NuxtLink :to="`/posts/1`">{{ post.title }}</NuxtLink>
    </h3>
    <div class="post-meta text-gray-700 flex items-center space-x-2">
      <!-- Display current date in human readable format -->
      <div>{{ new Date(post.created_at).toDateString() }}</div>
      <div>&middot;</div>
      <div>{{ post.user.name }}</div>
    </div>
    <div class="post-preview leading-relaxed mt-4">
      {{ post.body }}
    </div>
    <div class="mt-4">
      <NuxtLink
        :to="`/posts/1`"
        class="bg-blue-700 hover:bg-blue-800 text-white rounded inline-block px-4 py-2"
        >Read More</NuxtLink
      >
    </div>
  </div>
</template>
