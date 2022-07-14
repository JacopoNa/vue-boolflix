<template>
    <li>
        <div>Titolo: {{ item.title ? item.title : item.name }}</div>
        <div>Titolo originale: {{ item.original_title ?  item.original_title : item.original_name}}</div>
        <div>Lingua:
            <img v-if="available.includes(item.original_language)" class="flag" :src="require(`../assets/img/${item.original_language}.png`)" :alt="item.original_language"> 
            <span v-else>{{ item.original_language }}</span>
        </div>
        <div>Voto: {{ item.vote_average }}</div>
    </li>
</template>

<script>
export default {
    name: 'ContentComponent',
    data: function() {
        return {
            available: ['it', 'en']
        }
    },
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

        .flag {
            width: 30px;
        }
    }
</style>