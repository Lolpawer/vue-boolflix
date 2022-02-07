<template>
    <header>
        <h1 class="px-3">BOOLFLIX</h1>
        <div
        class="px-3">
            <input type="text"
            placeholder="Search"
            class="mx-2"
            v-model="userSearch"
            @keyup.enter="$emit('search', userSearch)">
            <button @click="$emit('search', userSearch)">
                Search
            </button>
        </div>
    </header>
</template>

<script>
export default {
    data() {
        return {
            userSearch: ""
        }
    }
}
</script>

<style lang="scss" scoped>
    header {
        background-color: #000000;
        width: 100%;

        h1 {
        color: #c60000;

        }
    }
</style>