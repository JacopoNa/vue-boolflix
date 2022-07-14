<template>
    <div class="main">
        <h3>FILM</h3>
        <ul class="cards d-flex flex-wrap">
            <ContentComponent v-for="content in movieCards" :key="content.id" :item="content"/>
        </ul>

        <h3>SERIE TV</h3>
        <ul class="cards d-flex flex-wrap">
            <ContentComponent v-for="content in seriesCards" :key="content.id" :item="content"/>
        </ul>
    </div>
</template>

<script>
import ContentComponent from './ContentComponent.vue';

export default {
    name: 'MainComponent',
    components: {
        ContentComponent
    },
    props: {
        "movieCards": Array,
        "seriesCards": Array
    }
}
</script>

<style lang="scss" scoped>
    .main {
        background-color: #1E1E1E;
        
        h3 {
            margin-left: 10px;
            color: white;
        }
    }
</style>