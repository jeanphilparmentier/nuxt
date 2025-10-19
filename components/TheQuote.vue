<script setup>
const props = defineProps({
  id: Number,
})
const {
  data: quote,
  pending,
  error,
} = await useFetch(() => `https://dummyjson.com/quotes/${props.id}`)
</script>

<template>
  <div>
    <p class="h-52" v-if="pending">Fetching...</p>
    <pre class="h-52" v-else-if="error">
Could not load quote: {{ error.data }}</pre
    >
    <figure v-else class="quote h-40 overflow-y-auto">
      <blockquote>{{ quote.quote }}</blockquote>
      <figcaption>&mdash; {{ quote.author }}</figcaption>
    </figure>
  </div>
</template>

<style scoped>
.quote {
  font: 1.25rem serif, system-ui;
  line-height: 150%;
  max-width: 60ch;
  margin: 1.5rem 0;
  padding: 1rem;
  border-radius: 0.5em;
  background: hsl(260, 60%, 96%);
  border: 1px solid hsl(260, 60%, 92%);
}
.quote figcaption,
.quote blockquote {
  margin: 1rem;
}
</style>
