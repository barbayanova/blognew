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
    padding: 10px;
    gap: 10px;
}
</style>
