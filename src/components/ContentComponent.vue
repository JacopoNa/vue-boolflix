<template>
    <li>
        <div>Titolo: {{ item.title }}</div>
        <div>Titolo originale: {{ item.original_title }}</div>
        <div>Lingua: {{ item.original_language }}</div>
        <div>Voto: {{ item.vote_average }}</div>
    </li>
</template>

<script>
export default {
    name: 'ContentComponent',
    props: {
        "item": Object
    }
}
</script>

<style lang="scss" scoped>
    li {
        list-style-type: none;
        margin: 10px;
        background-color: white;
    }
</style>