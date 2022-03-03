<template>
    <div class="dish">
        <h2>{{ dish.name }}</h2>
        <p>{{ dish.description }}</p>
        <p>Php {{ dish.price }}</p>
        <img class="dish__img" :src="dish.images[0].path" :alt="`${dish.id}_${dish.name}`" />
        <button>Order Now</button>
    </div>
</template>

<script>
export default {
    name: "Dish",
    props: {
        dish: {
            type: Object / Array,
            default: null,
        },
    },
};
</script>

<style>
.dish {
    margin-bottom: 5em;
    vertical-align: middle;
    border: 1px solid black;
    display: inline-block;
}
.dish__img {
    max-height: 100px;
}
</style>