<template>
    <nav class="navbar navbar-light bg-light">
        <a class="navbar-brand" href="#">
            <img src="../assets/logo.png" width="30" height="30" alt="" />
        </a>
        <span>We have {{numberOfPokemon}} pokemons!</span>
    </nav>
</template>

<script>
export default {
    name: "PokeNav",
    props: ["numberOfPokemon"]
}
</script>

<style scoped>

</style>