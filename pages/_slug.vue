<template>
  <div class="container">
    <img :src="planet.image" alt="" />
    <h1 class="title">{{ planet.title }}</h1>
    <NuxtLink to="/">Back to home</NuxtLink>
    <!-- <pre>{{ $data }}</pre> -->
  </div>
</template>

<script>
export default {
  async asyncData({params}) {
    const planet = await fetch(`https://api.nuxtjs.dev/planets/${params.slug}`).then((res) =>
      res.json()
    )
    return { planet }
  },
}
</script>

<style>
img {
    height: 80px;
    width: auto;
    
    /* object-fit: cover; */
    }
.container{
    margin-top: 100px;

    /* margin-bottom: 50%; */
    min-height: 100vh;
    text-align: center;
}
.title {
    font-family: 'Courier New', Courier, monospace;
}
</style>