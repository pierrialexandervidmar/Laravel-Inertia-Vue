<template>
  <div>
    <Link :href="route('home')" :class="{ 'font-bold': $page.url === '/home'}">Posts</Link> |
    <Link :href="route('about')" :class="{ 'font-bold': $page.url === '/about'}">Sobre</Link>
  </div>
</template>

<script>
import { Link } from '@inertiajs/vue3';
export default {
    name: 'MenuLayout',
    components: {
        Link
    }
}
</script>

<style scoped>

</style>