<template>
  <div>
    <h1>Estou na página Sobre nós</h1>
    <p>Meu nome é {{ name }}</p>

    <menu-layout />
  </div>
</template>

<script>
import { Link } from '@inertiajs/vue3'
import MenuLayout from '../Layouts/LayoutMenu.vue';

export default {
    name: 'PageAbout',
    components: {
        Link,
        MenuLayout
    },
    props: {
        name: String
    },
}
</script>

<style>

</style>