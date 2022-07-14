<template>
    <li>
        <div>
            <img v-if="item.poster_path" class="poster-img" :src="`https://image.tmdb.org/t/p/w342/${item.poster_path}`" alt="">
            <img v-else class="poster-img" src="https://en-it.ecolab.com/Areas/EcolabSite/img/catalog-default-img.gif" alt="">
        </div>
        <div>Titolo: {{ item.title ? item.title : item.name }}</div>
        <div>Titolo originale: {{ item.original_title ?  item.original_title : item.original_name}}</div>
        <div>Lingua:
            <img v-if="available.includes(item.original_language)" class="flag" :src="require(`../assets/img/${item.original_language}.png`)" :alt="item.original_language"> 
            <span v-else>{{ item.original_language }}</span>
        </div>
        <div>
            Voto: 
            <span v-for="n in ratingStars(item.vote_average)" :key="n">&#9733;</span>
            <span v-for="n in 5 - ratingStars(item.vote_average)" :key="n">&#9734;</span>
        </div>
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
    },
    methods: {
        ratingStars(original_vote) {
            let rounded = Math.round(original_vote / 2);
            console.log (rounded)
            return rounded
        }
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
        .poster-img {
            width: 200px;
            object-fit: cover;
        }
    }
</style>