<template>
    <nav>
        <ul>
            <li><nuxt-link to="/">Home</nuxt-link></li>
            <li><nuxt-link to="/blog">About</nuxt-link></li>
            <li><nuxt-link to="/contact">Contact</nuxt-link></li>
        </ul>
    </nav>
</template>

<style scoped>
ul {
    list-style: none;
    display: flex;
    justify-content: center;
    padding: 10px;
    gap: 30px;
    width: auto;
    background-color: #cf7272;
    font-size: 30px;
    text-decoration: none;
}
a {
    text-decoration: none;
    color: rgb(255, 255, 255);
}
</style>
