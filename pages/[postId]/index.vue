<template>
  <Suspense>
    <main>
      <h1>{{ article.title }}</h1>
      <p>
        <time :datetime="article.publishedAt" v-text="article.publishedAt" />
      </p>
      <div v-html="article.content" />
    </main>
  </Suspense>
</template>

<script setup lang="ts">
const route = useRoute();
const postId = route.params.postId;
const { data: article } = await useFetch(`/blog/${slug}`, {
  baseURL: 'https://tiamat.microcms.io/api/v1',
  headers: {
    'X-MICROCMS-API-KEY': 'cea0bdf6bfc54fbd8b53f3bfbbdc346710d8',
  },
});
</script>
