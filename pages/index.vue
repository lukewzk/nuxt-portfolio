<script setup>
const { data: posts } = await useAsyncData('latest-posts', () =>
  queryContent('/blog')
    .sort({ data: 1 })
    .limit(3)
    .find()
)
</script>

<template>
  <Head>
    <Title>Luke | Home</Title>
    <Meta name="description" content="This is my homepage" />
  </Head>

  <section>
    <h1 class="text-5xl font-bold mt-20">👋🏻 Hello, I'm Luke Wong!</h1>
    <p class="text-base text-gray-900 p-2 italic">Web Developer at Hiredly</p>
  </section>

  <section class="flex flex-col md:flex-row">
    <div class="md:w-3/4">
      <h2 class="text-3xl font-bold mt-8">My Story</h2>
      <p class="text-lg py-2">
        I am a Web Developer living just outside of one of my favorite places in the world, Petaling Jaya, Selangor. I am
        a
        self-taught programmer who firmly believes that you can accomplish anything in this life if you put your mind to
        it,
        roll up your sleeves and are willing to put in the work.
      </p>
      <p class="text-lg py-2">
        I have been doing web development for over 3+ years now and I am more than happy to help anyone that wants to
        learn about web development as a career choice.
      </p>
      <p class="text-lg py-2">
        In my personal life I enjoy
        reading,
        running and lifting weights to get me through the week.
      </p>
    </div>
    <img src="~/assets/images/luke-avatar.jpg" class="w-1/2 md:max-w-sm p-8 mx-auto rounded-full" />
  </section>

  <section>
    <h2 class="text-3xl font-bold mt-8">Latest Blog Posts</h2>
    <div class="grid md:grid-cols-3 pt-8 gap-10">
      <Post :posts="posts" />
    </div>
  </section>
</template>
