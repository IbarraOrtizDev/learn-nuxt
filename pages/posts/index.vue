<template>
  <h1>POSTS</h1>
  <section
  >
    <article
      v-for="post in posts"
      :key="post.id"
      class="my-4 mx-2 p-4 border-2"
    >
      <nuxt-link :to="`/posts/${post.id}`">

        <h2 class="mb-2 text-xl bold">{{ post.title }}</h2>
        <p>{{ post.body }}</p>
      </nuxt-link>
    </article>
  </section>
</template>
<script setup>
/* COMO UNA SPA */
// const data = await fetch('https://jsonplaceholder.typicode.com/posts')
//   .then((res) => res.json())
//   .then((data) => {
//     posts.value = data
//   })

/* COMO UN SSR */
const {data:posts } = useFetch('https://jsonplaceholder.typicode.com/posts')


</script>