<template>
    <nav>
        <ul>
            <li>
                <router-link to="/" exact>博客</router-link>
                <router-link to="/add" exact>创建博客</router-link>
            </li>
        </ul>
    </nav>
</template>

<script>
    export default {
        name: 'blog-header',
    }
</script>

<style>

</style>

