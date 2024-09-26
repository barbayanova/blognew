<template>
    <h2>Блог</h2>
    <main>
        <article v-for="post in posts" :key="post.id">
            <h3> {{ post.title }} </h3>
            <img :src=base_url+post.img.url alt="Облошка статьи">
            <p>{{ post.desc }}</p>
            <NuxtLink to="">Подробнее</NuxtLink>
        </article>
    </main>

</template>
<script setup>
    const api = await $fetch('http://localhost:1337/api/posts/?populate=*')
    const posts = api.data

    const base_url = "http://localhost:1337"
</script>

<style scoped>
main {
    display: flex;
    gap: 10px;
}
article {
    background-color: wheat;
    padding: 10px;
}
</style>