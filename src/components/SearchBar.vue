<template>
    <div>
        <input type="text"
        placeholder="Search"
        class="mx-2"
        v-model="userSearch">
        <button @click="$emit('search', userSearch)">
            Search
        </button>
    </div>
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
</style>