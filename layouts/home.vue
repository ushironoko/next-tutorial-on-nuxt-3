<script setup lang="ts">
const name = "Ushironoko";
const siteTitle = "Learn how to build a personal website using Nuxt3";
</script>

<template>
  <div class="container">
    <Head>
      <Title>{{ siteTitle }}</Title>
      <Link rel="icon" href="/images/profile.jpeg" />
      <Meta
        name="description"
        content="Learn how to build a personal website using Next.js"
      />
      <Meta
        property="og:image"
        :content="`https://og-image.vercel.app/${encodeURI(
          siteTitle
        )}.png?theme=light&md=0&fontSize=75px&images=https%3A%2F%2Fassets.vercel.com%2Fimage%2Fupload%2Ffront%2Fassets%2Fdesign%2Fnextjs-black-logo.svg`"
      />
      <Meta name="og:title" :content="siteTitle" />
      <Meta name="twitter:card" content="summary_large_image" />
    </Head>
    <header class="header">
      <img
        priority
        src="/images/profile.jpeg"
        class="borderCircle"
        height="144"
        width="144"
        alt=""
      />
      <h1 class="heading2Xl">{{ name }}</h1>
    </header>
    <main><slot /></main>
  </div>
</template>

<style lang="scss" scoped>
@use "~/assets/styles/utils.scss";

.container {
  max-width: 36rem;
  padding: 0 1rem;
  margin: 3rem auto 6rem;
}
.header {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
