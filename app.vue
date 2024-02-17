<script setup>
useHead({
  title: 'YekJaModir',
  meta: [
    { name: 'description', content: 'yek ja modir' },
  ],
  links: [
    { rel: "stylesheet", type: "text/css", href: 'https://cdn.jsdelivr.net/gh/rastikerdar/samim-font@v4.0.5/dist/font-face.css' },
  ]
})
</script>

<template>
  <NuxtLayout>
    <v-app>
      <NuxtPage />
    </v-app>
  </NuxtLayout>
</template>

<style>

.font-samim {
  font-family: 'Samim', sans-serif;
}
</style>