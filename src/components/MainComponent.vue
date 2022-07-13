<template>
    <div class="main">
        <ul class="cards d-flex flex-wrap">
            <ContentComponent v-for="content in movieCards" :key="content.id" :item="content"/>
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
    }
}
</script>

<style lang="scss" scoped>
    .main {
        height: 100vh;
        background-color: grey;        
    }
</style>