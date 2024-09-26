<template>
        <h2>Главная страница</h2>
    <!-- <main>
        <article v-for="post in posts" :key="post.id">
            {{ post.titile }}
            <img src="https://www.terekalmaz.by/wp-content/uploads/galka.png" alt="" >
            <ul>
                <li v-for="tag in post.tags" :key="post.id">
                    {{ tag }}
                </li>
            </ul>
        </article>
    </main> -->
</template>

<!-- <style scoped>
main {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap:20px;
}
article {
    border-radius: 10px;
    background-color: brown;
    color: wheat;
    padding: 10px;
}

article img {
    width: 100px;
    height: 180px;
    object-fit: cover;
}
article a {
    padding: 10px;
    background-color: wheat;
    color: brown;
    text-decoration: none;
    text-align:  center;
    display: block;
}

</style> -->

<script setup>
const dataTwice = await $fetch("https://dummyjson.com/posts")
const posts = dataTwice.posts
</script>