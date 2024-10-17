<template>
    <nav>
        <ul>
            <li><NuxtLink to="/blog">Блог</NuxtLink></li>
            <li><NuxtLink NuxtLink :style="'background-color:'+post.categories[0].bg" :to="'/category/' + post.categories[0].documentId">{{ post.categories[0].title }}</NuxtLink></li>
            <li>{{ post.title }}</li>
        </ul>
    </nav>
    <main>
        <h1>{{ post.title }}</h1>
        <img :src=base_url+post.img.url alt="">
        <div v-html="mark"></div>
    </main>
</template>

<script setup>
import MarkdownIT from "markdown-it"
const markdown = new MarkdownIT()

const {id} = useRoute().params

const api = await $fetch(`http://localhost:1337/api/posts/${id}?populate=*`)
const post = api.data;
const mark = markdown.render(post.body);

const base_url = 'http://localhost:1337'

const apiConfig = await $fetch (`${base_url}/api/config?`)
const config = apiConfig.data
useHead({
    title: `${post.title} - ${config.title}`
})
</script>

<style scoped>
li::before {
    content: ">";
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
li {
    text-decoration: none;
}
main {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
}
div {
    padding: 20px;
    font-size: 20px;

}
</style>
