<template>
<div>
   <NuxtLogo />
   <h1 class="title">Dynamic Page </h1>
  <NuxtLink to="/">Back to home</NuxtLink>
  <pre>{{data}}</pre>
</div>
 
</template>

<script>
export default {
    async asyncData() {
        const planet = await fetch('https://api.nuxtjs.dev/planets').then((res) => res.json())
        return { planet }
}
}
</script>
