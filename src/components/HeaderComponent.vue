<template>
    <header class="d-flex justify-content-between align-items-center">
        <div>
            <h2>BOOLFLIX</h2>
        </div>
        <div class="search-bar">
            <input type="text" v-model="inputText" placeholder="Cerca un film..." @keyup.enter="$emit('componentSearch', inputText)">
            <button @click="$emit('componentSearch', inputText)">Cerca</button>
        </div>
    </header>
</template>

<script>
export default {
    name: 'HeaderComponent',
    data: function() {
        return {
            inputText: ''
        }
    }   
}
</script>

<style lang="scss" scoped>
    header{
        height: 100px;
        background-color: black;
        color: white;

        h2 {
            color: red;
            margin-left: 20px;
        }
        .search-bar {
            margin-right: 20px;
        }
    }
</style>