<template>
  <div>
    <Head>
        <title>Sobre Nós</title>
    </Head>
    <h1>Estou na página Sobre nós</h1>
    <p>Meu nome é {{ name }}</p>

    <menu-layout />
  </div>
</template>

<script>
import { Link, Head } from '@inertiajs/vue3'
import MenuLayout from '../Layouts/LayoutMenu.vue';

export default {
    name: 'PageAbout',
    components: {
        Link,
        MenuLayout,
        Head
    },
    props: {
        name: String
    },
}
</script>

<style>

</style>