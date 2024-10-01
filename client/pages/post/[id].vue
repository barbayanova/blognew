<template>
    <main>
        <h1>{{ post.title }}</h1>
        <img :src=base_usr+post.img.url alt="">
        <div v-html="mark"></div>
    </main>
</template>

<script setup>
import MarkdownIT from "markdown-it"
const markdown = new MarkdownIT()



const {id} = useRoute().params
const api = await $fetch('http://localhost:1337/api/posts?populate=*')
const post = api.data[id]
const mark = post.body

const base_usr = 'http://localhost:1337'
</script>

<style scoped>
img {
    width: 765px;
}
</style>
