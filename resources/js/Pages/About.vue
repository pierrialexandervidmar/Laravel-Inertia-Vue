<template>
  <div>
    <h1>Estou na página Sobre nós</h1>
    <p>Meu nome é {{ name }}</p>
  </div>
</template>

<script>
export default {
    name: 'PageAbout',
    props: {
        name: String
    },
}
</script>

<style>

</style>