<script setup>
const { data: posts } = await useAsyncData('posts', () =>
  queryContent('/blog').find()
)
</script>

<template>
  <Head>
    <Title>Luke | Blogs</Title>
    <Meta name="description" content="This is a list of blogs I wrote." />
  </Head>
  
  <h1 class="text-3xl my-8">Blog Posts</h1>
  I like to write about anything that I am currently working on or something new that interests me.
  <section class="grid md:grid-cols-3 mt-8 gap-10">
    <Post :posts="posts" />
  </section>
</template>
