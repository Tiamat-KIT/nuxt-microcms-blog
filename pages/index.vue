<script setup lang="ts">
const { data: posts, error } = await useFetch('/blog', {
  baseURL: 'https://tiamat.microcms.io/api/v1',
  headers: {
    'X-MICROCMS-API-KEY': 'cea0bdf6bfc54fbd8b53f3bfbbdc346710d8',
  },
});
</script>

<template>
  <div>
    <h3>MicroCMS＋Nuxt3 SSG</h3>
    <ol>
      <li v-for="article in posts?.contents" :key="artivle.id">
        <nuxt-link :to="`/${article.id}`">{{ article.title }}</nuxt-link>
        {{ console.log(article) }}
      </li>
    </ol>
  </div>
</template>
