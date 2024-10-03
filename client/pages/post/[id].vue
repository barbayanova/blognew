<template>
    <nav>
        <ul>
            <li><NuxtLink to="/blog">Блог</NuxtLink></li>
            <li><NuxtLink :to="'/category/'+ post.categories[0].id">{{ post.categories[0].title }}</NuxtLink></li>
            <li>{{ post.title }}</li>
        </ul>
    </nav>
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
li::before {
    content: ">>";
    margin-right: 10px;
}
li:first-child::before {
    display: none;
}
img {
    width: 765px;
}
nav ul {
    list-style: none;
    display: flex;
    gap:10px;
}
</style>
