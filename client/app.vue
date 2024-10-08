<template>
    <Navbar />
    <NuxtPage />
    <Footer />
</template>
<script setup>
const base = 'http://localhost:1337'
const api = await $fetch(`${base}/api/config?popuate=*`)
const config = api.data

useHead ({
    title:config.title,
    meta: [
        {name:'decription', content:config.desc},
        {name:'keywords', content:config.keywords},
    ],
    link: [
        {rel:'icon', tupe: 'image/x-icon' , href: bade+config.favicon.url},
    ]
})
</script>

<style>
html, body, #_nuxt {
    width: 100%;
    height: 100%;
    margin: auto;
    display: flex;
    flex-direction:column;
}
main {
    flex:1 1 auto;
}
</style>
