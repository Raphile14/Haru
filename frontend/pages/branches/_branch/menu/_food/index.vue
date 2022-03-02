<template>
    <div class="main"><p>food</p></div>
</template>

<script>
export default {
    name: "Food",
    head() {
        return {
            title: `${this.$route.params.food} | Haru`,
        };
    },
};
</script>

<style>
</style>