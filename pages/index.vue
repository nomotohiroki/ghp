<template>
  <ul>
    <li v-for="article in articles" :key="article.slug">
      <NuxtLink :to="article.slug">{{ article.title }}</NuxtLink>
    </li>
  </ul>
</template>

<script>
export default {
  async asyncData ({ $content, params }) {
    const articles = await $content('articles').limit(10).fetch()
    console.log(articles)
    return { articles }
  }
}
</script>
