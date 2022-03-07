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
                    </div>
                    <NuxtLink to="/branches/makati/menu"
                        ><button class="primary__button shrink">
                            Order Now
                        </button></NuxtLink
                    >
                </div>
                <!-- <img
                    :src="homepage.banner.image[0].path"
                    :alt="homepage.banner.image[0].alt"
                /> -->
                <!-- <img
                    :src="homepage.banner.image[1].path"
                    :alt="homepage.banner.image[1].alt"
                /> -->
            </div>

            <div class="category">
                <div
                    class="recent_category"
                    v-for="index in homepage.recent_categories"
                    :key="`recent_category_${index.id}`"
                >
                    <h2>{{ index.name }}</h2>
                    <img
                        :src="index.image.path"
                        :alt="`${index.id}_${index.name}`"
                    />
                </div>
            </div>

            <div class="best__seller__products">
                <div>
                    <h2>Best Sellers</h2>
                    <p>Try our most popular dishes</p>
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
                <div>
                    <h2>{{ homepage.featured_category_products.name }}</h2>
                    <p>{{ homepage.featured_category_products.description }}</p>
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
                <div>
                    <h2>Haru Party Trays</h2>
                    <p>
                        Perfect for every occassion. Call us to order and have
                        it delivered straight to your home.
                    </p>
                    <button>Call to Order</button>
                    <button>Download Party Menu</button>
                    <img
                        :src="homepage.featured_content.image_url"
                        alt="party__trays"
                    />
                </div>
            </div>

            <div class="follow__ig">Follow us on Instagram</div>
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
.overlay {
    position: absolute;
    /* top: 50%; */
    left: 0;
    right: 0;
    width: 100%;
    max-width: calc(100% - 120px);
    margin: 0 auto;
    transform: translateY(200%);
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

div.index > div > div {
    margin-bottom: 5em;
}

.recent_category {
    margin-bottom: 5em;
    vertical-align: middle;
    border: 1px solid black;
    display: inline-block;
}

.featured__container,
.best__seller__container {
    padding: 0 calc(7% - 10px) 10px;
    overflow: hidden;
    position: relative;
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
</style>
