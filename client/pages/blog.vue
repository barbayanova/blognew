<template>
    <h2>Блог</h2>
    <main>
        <article v-for="(post, index) in posts" :key="post.id">
            <h3> {{ post.title }} </h3>
            <img :src=base_url+post.img.url :alt=post.img.alternativeText>
            <p>{{ post.desc }}</p>
            <NuxtLink :to="'/post/' + index">Подробнее</NuxtLink>
        </article>
    </main>

</template>
<script setup>
    const api = await $fetch('http://localhost:1337/api/posts/?populate=*')
    const posts = api.data

    const base_url = "http://localhost:1337"
</script>

<style scoped>
@media screen and (max-width:1024px) {
    .posts {
        display: grid;
        grid-template-columns: (3, 1fr);
        gap:25px;
    }
    
}
/* main {
    display: flex;
    gap: 10px;
} */
article {
    height: 100%;
    background-color: wheat;
    width:auto;
    padding: 10px;
}
article img {
    width: 100%;
}

article p {
height: 100%;
}

article a {
    display: block;
}
</style>