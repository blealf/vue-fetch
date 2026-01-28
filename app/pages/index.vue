<template>
  <div class="max-w-292.5 mx-auto px-5">
    <h1 class="text-4xl py-5 font-extrabold">
      Latest Business News
    </h1>

    <div
      v-if="articles.length && !pending"
      class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6"
    >
      <NewsItem
        v-for="item in articles"
        :key="item.url"
        :item="item"
      />
    </div>

    <div
      v-else-if="pending"
      class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6"
    >
      <NewsItemSkeleton
        v-for="i in 8"
        :key="i"
      />
    </div>

    <p
      v-else-if="error"
      class="text-red-500"
    >
      Failed to load news.
    </p>
  </div>
</template>

<script lang="ts" setup>
const config = useRuntimeConfig()
const apiUrl = config.public.apiUrl
const apiKey = config.public.apiKey

type NewsArticle = {
  source: {
    id: string | null
    name: string
  }
  author: string | null
  title: string
  description: string | null
  url: string
  urlToImage: string | null
  publishedAt: string
  content: string | null
}

const { data, pending, error } = useAsyncData(
  'news',
  () => $fetch<{ articles: NewsArticle[] }>(`${apiUrl}&apiKey=${apiKey}`)
)

const articles = computed<NewsArticle[]>(() => {
  return data.value?.articles ?? []
})
</script>
