<template>
    <div class="dish swiper-slide disc__exact">
        <NuxtLink :to="`/branches/makati/menu${dish.slug}`">
            <div class="dish__inner">
                <div class="dish__image__holder">
                    <img
                        class="dish__img"
                        :src="dish.images[0].path"
                        :alt="`${dish.id}_${dish.name}`"
                    />
                </div>
                <div class="dish__description">
                    <div class="dish__text">
                        <h2 class="dish__title">{{ dish.name }}</h2>
                        <p class="dish__subtitle" v-html="dish.description"></p>
                        <h3 class="dish__price">Php {{ dish.price }}</h3>
                    </div>
                </div>
                <div class="dish__button__container">
                    <button class="dish__button">Order Now</button>
                </div>
            </div>
        </NuxtLink>
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
    /* border: 1px solid black; */
    display: inline-block;
}
.dish__img {
    /* max-height: 100px; */
    width: 100%;
    height: auto;
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
}

.disc__exact {
    width: 324px;
    margin-right: 20px;
}

.swiper-slide {
    flex-shrink: 0;
    /* width: 100%; */
    height: 100%;
    position: relative;
    transition-property: transform;
}

.dish__inner {
    width: 100%;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 5px 5px 15px rgb(51 42 17 / 10%);
    padding-bottom: 0;
    border: 1px solid transparent;
    transition: 0.2s ease-out;
}

.dish__image__holder {
    position: relative;
    overflow: hidden;
}

.dish__description {
    background-color: var(--white);
    padding: 10px 25px;
}

.dish__title,
.dish__subtitle {
    display: -webkit-box;
    -webkit-box-orient: vertical;
    overflow: hidden;
    word-break: break-all;
    text-overflow: ellipsis;
    -webkit-line-clamp: 2;
}

.dish__title {
    font-family: Karla-Bold;
    font-size: 30px;
    line-height: 35px;
    color: var(--secondary);
    height: 70px;
    max-width: 245px;
    overflow: hidden;
    margin-bottom: 10px;
    word-break: break-word !important;
}

.dish__subtitle {
    font-family: Karla-Regular;
    font-size: 18px;
    line-height: 26px;
    height: 50px;
    margin-bottom: 10px;
    word-break: break-word !important;
}
.dish__price {
    font-family: Karla-Bold;
    font-size: 25px;
    color: var(--secondary);
}
.dish__button__container {
    margin-top: 45px;
}

.dish__button {
    padding: 16px 30px;
    background-color: var(--primary);
    color: var(--white);
    font-family: Karla-Regular;
    font-size: 20px;
    border-radius: 100px;
    margin-bottom: 10px;
}
</style>