<template>
  <div>
    <h1>Estou na Home! Deu boaaaaa</h1>
    <ul>
        <li v-for="post in posts" :key="post.id">
            <h2>
                {{ post.id }} - {{ post.title }}
            </h2>
            <p>
                {{ post.content }}
            </p>
        </li>
    </ul>
  </div>
</template>

<script>
export default {
    name: "PageHome",
    props: {
        posts: Object
    }

};
</script>

<style>
</style>