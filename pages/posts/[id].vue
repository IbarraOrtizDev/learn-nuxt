<template>
  <div>
    <h1>{{ route.params.id }}</h1>
    <h2 class="mb-2 text-xl bold">{{ post.title }}</h2>
    <p>{{ post.body }}</p>
  </div>
</template>
<script setup>
  const route = useRoute();

  const { data: post } =await useFetch(
    `https://jsonplaceholder.typicode.com/posts/${route.params.id}`
  );
</script>