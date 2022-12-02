<script setup lang="ts">
const { params } = useRoute();

const id = Array.isArray(params.id) ? params.id[0] : params.id;

const { data } = useFetch(`/api/posts/postData?id=${encodeURIComponent(id)}`, {
  key: id,
});
</script>

<template>
  <h1>{{ params.id }}</h1>
  <div class="whitespace-pre-wrap" v-html="data?.contentHtml"></div>
</template>

<style lang="scss">
@use "~/assets/styles/utils.scss";
</style>
