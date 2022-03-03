<template>
    <div id="default">
        <NavHeader :branches="branches" />
        <Nuxt />
        <Footer />
    </div>
</template>

<script>
export default {
    name: "Default",
    data() {
        return {
            branches: [],
        };
    },
    async fetch() {
        // Get Branches
        await this.$axios
            .get(
                "https://dbresto-api.designbluemanila.com/api/frontend/branches"
            )
            .then((res) => {
                this.branches = res.data.data;
            })
            .catch((err) => {
                console.log(err);
                alert("Failed to get branches");
            })
            .then(() => {
                // console.log(this.branches);
            });
    },
};
</script>

<style>
</style>