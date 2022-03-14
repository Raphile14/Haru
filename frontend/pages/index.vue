<template>
    <div class="index">
        <div v-if="$fetchState.pending">content loading</div>
        <div v-else>
            <div
                class="front"
                :style="`background-image: url(${homepage.banner.image[0].path})`"
            >
                <div class="overlay">
                    <div class="front__text">
                        <h2 class="title secondary__text">
                            {{ homepage.banner.label }}
                        </h2>
                        <p>{{ homepage.banner.description_text }}</p>
                        <NuxtLink to="/branches/makati/menu"
                            ><button class="primary__button shrink">
                                Order Now
                            </button></NuxtLink
                        >
                    </div>
                </div>
            </div>

            <div class="category">
                <div class="category__container">
                    <div class="swiper-container">
                        <div class="swiper-wrapper category__swipper">
                            <NuxtLink
                                :to="`/branches/makati/menu?category=${index.slug}`"
                                class="recent_category"
                                v-for="index in homepage.recent_categories"
                                :key="`recent_category_${index.id}`"
                            >
                                <img
                                    class="category__img"
                                    :src="index.image.path"
                                    :alt="`${index.id}_${index.name}`"
                                />
                                <h2 class="category__title">
                                    {{ index.name }}
                                </h2>
                            </NuxtLink>
                        </div>
                    </div>
                </div>
            </div>

            <div class="best__seller__products">
                <div class="best__seller__header">
                    <div class="">
                        <h2 class="best__seller__header__title">
                            Best Sellers
                        </h2>
                    </div>
                    <div class="best__seller__header__description__container">
                        <p class="best__seller__header__description">
                            Try our most popular dishes
                        </p>
                    </div>
                </div>
                <div class="best__seller__container">
                    <div class="best__seller__dish__container swiper-container">
                        <div class="swiper-wrapper">
                            <Dish
                                class="best_dish"
                                v-for="index in homepage.best_sellers"
                                :key="`best_seller_${index.id}`"
                                :dish="index"
                            />
                        </div>
                    </div>
                    <div
                        data-v-064b630d=""
                        slot="button-next"
                        class="
                            swiper-button-next
                            swiper-button-nextcategory_products
                            __css_lebIk2bH __css_LXf4ywGe
                        "
                        tabindex="0"
                        role="button"
                        aria-label="Next slide"
                        aria-disabled="false"
                    ></div>
                </div>
            </div>

            <div class="featured__category__products">
                <div class="best__seller__header">
                    <div>
                        <h2 class="best__seller__header__title">
                            {{ homepage.featured_category_products.name }}
                        </h2>
                    </div>
                    <div class="best__seller__header__description__container">
                        <p class="best__seller__header__description">
                            {{
                                homepage.featured_category_products.description
                            }}
                        </p>
                    </div>
                </div>

                <div class="featured__container">
                    <div class="featured__dish__container swiper-container">
                        <div class="swiper-wrapper">
                            <Dish
                                class="featured__dish"
                                v-for="index in homepage
                                    .featured_category_products.product"
                                :key="`featured_category_products${index.id}`"
                                :dish="index"
                            />
                        </div>
                    </div>
                    <div
                        data-v-064b630d=""
                        slot="button-next"
                        class="
                            swiper-button-next
                            swiper-button-nextcategory_products
                            __css_lebIk2bH __css_LXf4ywGe
                        "
                        tabindex="0"
                        role="button"
                        aria-label="Next slide"
                        aria-disabled="false"
                    ></div>
                </div>
            </div>

            <div class="party__trays">
                <div class="party__trays__desc">
                    <div class="party__trays__left">
                        <h2 class="party__trays__title">Haru Party Trays</h2>
                        <p class="party__trays__left__desc">
                            Perfect for every occassion. Call us to order and
                            have it delivered straight to your home.
                        </p>
                    </div>
                    <div class="party__trays__button__container">
                        <button class="party__trays__button">
                            Call to Order
                        </button>
                        <button class="party__trays__button__download">
                            <svg
                                id="Component_33_1"
                                data-name="Component 33 – 1"
                                xmlns="http://www.w3.org/2000/svg"
                                width="40"
                                height="40"
                                viewBox="0 0 40 40"
                                class="party__trays__button__comp"
                            >
                                <g
                                    id="Ellipse_97"
                                    data-name="Ellipse 97"
                                    fill="#da2519"
                                    stroke="#da2519"
                                    stroke-width="1"
                                >
                                    <circle
                                        cx="20"
                                        cy="20"
                                        r="20"
                                        stroke="none"
                                    ></circle>
                                    <circle
                                        cx="20"
                                        cy="20"
                                        r="19.5"
                                        fill="none"
                                    ></circle>
                                </g>
                                <path
                                    id="Icon_awesome-arrow-down"
                                    data-name="Icon awesome-arrow-down"
                                    d="M16.492,9.775l.877.877a.944.944,0,0,1,0,1.339L9.694,19.67a.944.944,0,0,1-1.339,0L.676,11.991a.944.944,0,0,1,0-1.339l.877-.877a.949.949,0,0,1,1.355.016l4.535,4.76V3.2A.946.946,0,0,1,8.39,2.25H9.655A.946.946,0,0,1,10.6,3.2V14.551l4.535-4.76a.942.942,0,0,1,1.355-.016Z"
                                    transform="translate(10.977 8.9)"
                                    fill="#fff"
                                ></path>
                            </svg>
                            Download Party Menu
                        </button>
                    </div>
                </div>
                <div class="party__trays__image">
                    <img
                        src="/images/home-featured-image.png"
                        alt="party__trays"
                    />
                </div>
            </div>

            <div class="follow__ig">
                <div class="follow__header">
                    <h2 class="follow__title">Follow us on Instagram</h2>
                    <div class="follow__right">
                        <img
                            class="follow__ig__img"
                            src="/images/socials/ig.png"
                            alt="ig"
                        />
                        <h2 class="follow__ig__title">haru</h2>
                    </div>
                </div>
                <div class="follow__ig__img__below swiper-container">
                    <div class="swiper-wrapper">
                        <div class="swiper-slide follow__ig__img__col">
                            <img
                                class="follow__img"
                                src="/images/home/postone.png"
                                alt=""
                            />
                        </div>
                        <div class="swiper-slide follow__ig__img__col">
                            <img
                                class="follow__img"
                                src="/images/home/posttwo.png"
                                alt=""
                            />
                        </div>
                        <div class="swiper-slide follow__ig__img__col">
                            <img
                                class="follow__img"
                                src="/images/home/postthree.png"
                                alt=""
                            />
                        </div>
                        <div class="swiper-slide follow__ig__img__col">
                            <img
                                class="follow__img"
                                src="/images/home/postfour.png"
                                alt=""
                            />
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "IndexPage",
    head() {
        return {
            title: "Home | Haru",
        };
    },
    data() {
        return { homepage: {} };
    },
    async fetch() {
        // Get Makati Homepage Data
        await this.$axios
            .get(
                "https://dbresto-api.designbluemanila.com/api/frontend/homepage/makati"
            )
            .then((res) => {
                this.homepage = res.data.data;
            })
            .catch((err) => {
                console.log(err);
                alert("Failed to get homepage data");
            })
            .then(() => {
                // console.log(this.homepage);
            });
    },
};
</script>

<style>
.title {
    font-family: Karla-Bold;
    line-height: 51px;
    font-size: 51px;
}

.overlay {
    position: absolute;
    /* top: 50%; */
    left: 0;
    right: 0;
    width: 100%;
    max-width: calc(100% - 120px);
    margin: 0 auto;
    transform: translateY(100%);
}

.front__text {
    max-width: 50%;
    padding: 0 30px;
}

.shrink {
    max-width: 200px;
}

.front {
    height: 100vh;
    background-size: cover;
    background-repeat: no-repeat;
}

.front .primary__button {
    margin-top: 18px;
    padding: 10px 50px;
}

.featured__container,
.best__seller__container {
    padding: 0 calc(7% - 10px) 10px;
    overflow: hidden;
    position: relative;
}

.best__seller__header {
    opacity: 1;
    padding: 0 calc(7% - 10px) 40px;
}

.best__seller__header__title {
    color: var(--text_dark_primary);
    font-family: Karla-Bold;
    font-size: 50px;
    margin-top: 0;
    margin-bottom: 0;
}

.best__seller__header__description__container {
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.best__seller__header__description {
    font-family: Karla-Regular;
    font-size: 25px;
    color: var(--secondary);
    opacity: 0.6;
}

.featured__dish,
.best_dish {
    position: relative;
}

.featured__dish__container,
.best__seller__dish__container {
    overflow: visible !important;
}

.swiper-container {
    margin-left: auto;
    margin-right: auto;
    position: relative;
    overflow: hidden;
    list-style: none;
    padding: 0;
    z-index: 1;
}

.swiper-wrapper {
    position: relative;
    width: 100%;
    height: 100%;
    z-index: 1;
    display: flex;
    transition-property: transform;
    box-sizing: content-box;
}

.category {
    opacity: 1;
    margin: 50px 0;
}

.category__container {
    overflow: hidden;
    position: relative;
}

.category__swipper {
    overflow: visible !important;
    padding: 0 calc(7% - 10px) 10px;
}

.recent_category {
    width: 331.667px;
    margin-right: 10px;
    position: relative;
}

.category__img {
    height: 240px;
    width: 100%;
    -o-object-fit: cover;
    object-fit: cover;
}

.category__title {
    font-family: Karla-Bold;
    font-size: 32px;
    color: var(--white);
    position: absolute;
    top: 50%;
    right: 50%;
    transform: translate(50%, -50%);
}

.party__trays {
    display: flex;
    margin: 100px calc(8% - 20px) 0;
    overflow: hidden;
}

.party__trays__left {
    margin-bottom: 30px;
}

.party__trays__left__desc {
    font-family: Karla-Regular;
    font-size: 25px;
    color: var(--secondary);
    opacity: 0.6;
}

.party__trays__title {
    font-family: Karla-Bold;
    font-size: 50px;
    color: var(--secondary);
    margin-bottom: 10px;
}

.party__trays__image {
    border-radius: 10px;
    overflow: hidden;
}

.party__trays__desc {
    flex: 0 0 calc(45% - 10px);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin-right: 25px;
}

.party__trays__button {
    color: #f0f0f0;
    background-color: var(--primary);
    border: 1px solid var(--primary);
    font-family: Karla-Regular;
    font-size: 20px;
    border-radius: 100px;
    margin: 5px 0;
    padding: 15px 0;
    max-width: 350px;
}

.party__trays__button__download {
    color: var(--primary);
    background-color: var(--white);
    position: relative;
    border: 1px solid var(--primary);
    font-family: Karla-Regular;
    font-size: 20px;
    border-radius: 100px;
    margin: 5px 0;
    padding: 15px 0;
    max-width: 350px;
}

.party__trays__button__comp {
    position: absolute;
    left: 10px;
    top: 6px;
}

.party__trays__button__container {
    width: 100%;
    display: flex;
    flex-direction: column;
}

.party__trays__image > img {
    height: 100%;
    width: 100%;
}

.follow__ig {
    margin: 80px calc(8% - 18px) 0;
}

.follow__header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 50px;
}

.follow__title {
    font-family: Karla-Bold;
    color: var(--secondary);
    font-size: 50px;
}

.follow__right {
    display: flex;
    align-items: center;
}

.follow__ig__img {
    max-width: 30px;
}

.follow__ig__title {
    color: #9c9b99;
    margin-left: 10px;
    font-family: Karla-Bold;
    font-size: 24px;
}

.follow__ig__img__below {
    margin-left: auto;
    margin-right: auto;
    position: relative;
    overflow: hidden;
    list-style: none;
    padding: 0;
    z-index: 1;
}

.follow__ig__img__col {
    width: 24%;
    margin-right: 20px;
}

.follow__img {
    border-radius: 10px;
}
</style>
