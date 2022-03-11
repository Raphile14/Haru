<template>
    <div class="main dish__food__container">
        <div v-if="$fetchState.pending">content loading</div>
        <div v-else>
            <div class="main_container">
                <div id="breadcrumb">
                    <ul>
                        <li>
                            <NuxtLink to="/" class="breadcrumb__link">
                                HOME
                            </NuxtLink>
                            <span class="slash"> / </span>
                        </li>
                        <li>
                            <NuxtLink to="/branches" class="breadcrumb__link">
                                BRANCHES
                            </NuxtLink>
                            <span class="slash"> / </span>
                        </li>
                        <li>
                            <NuxtLink
                                to="/branches/makati/menu"
                                class="breadcrumb__link"
                            >
                                MAKATI
                            </NuxtLink>
                            <span class="slash"> / </span>
                        </li>
                        <li>
                            <NuxtLink
                                to="/branches/makati/menu"
                                class="breadcrumb__link"
                            >
                                <span class="breadcrumb__link">MENU</span>
                            </NuxtLink>
                            <span class="slash"> / </span>
                        </li>
                        <li>
                            <NuxtLink
                                :to="`/branches/makati/menu/${title}`"
                                class="breadcrumb__link"
                            >
                                <span class="breadcrumb__link__active">{{
                                    title
                                }}</span>
                            </NuxtLink>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="dish__food__inner">
                <div class="dish__food__div">
                    <div class="dish__food__details">
                        <div class="dish__food__left">
                            <div class="left__food__img__container">
                                <img :src="food.images[0].path" alt="" />
                            </div>
                        </div>
                        <div class="dish__food__right">
                            <div class="dish__food__title dish__food__row">
                                <h1 class="dish__food__h1">
                                    {{ title }}
                                </h1>
                                <p
                                    class="dish__food__description"
                                    v-html="food.description"
                                ></p>
                                <label for="" class="dish__food__price"
                                    >Php. {{ food.price }}</label
                                >
                            </div>
                            <div class="dish__food__row">
                                <div class="dish__food__quantity">
                                    <h2 class="dish__food__miniheader">
                                        Quantity
                                    </h2>
                                    <div
                                        class="dish__food__quantity__controller"
                                    >
                                        <div
                                            class="dish__food__quantity__button"
                                        >
                                            <div
                                                class="dish__food__symbol"
                                            ></div>
                                        </div>
                                        <div
                                            class="dish__food__quantity__count"
                                        >
                                            1
                                        </div>
                                        <div
                                            class="dish__food__quantity__button"
                                        >
                                            <div
                                                class="dish__food__symbol"
                                            ></div>
                                            <div
                                                class="
                                                    dish__food__symbol
                                                    dish__food__rotate
                                                "
                                            ></div>
                                        </div>
                                    </div>
                                </div>
                                <div
                                    v-if="food.addons.length > 0"
                                    class="dish__food__variations"
                                >
                                    <span class="dish__food__variations__title"
                                        >Variations</span
                                    >
                                    <div
                                        class="dish__food__variations__options"
                                        v-for="index in food.addons"
                                        :key="`options__${index}`"
                                    >
                                        <div class="dfv__left">
                                            <div class="dfv__button__outer">
                                                <span
                                                    class="dfv__button"
                                                ></span>
                                            </div>
                                            <label class="dfv__left__title">{{
                                                index.name
                                            }}</label>
                                        </div>
                                        <div class="dfv__right">
                                            P. {{ index.price }}
                                        </div>
                                    </div>
                                </div>
                            </div>
                            <div
                                v-if="food.meal_addons.length > 0"
                                class="dish__food__row"
                            >
                                <div class="dish__food__variations">
                                    <span class="dish__food__variations__title"
                                        >Add-ons</span
                                    >
                                    <span
                                        class="dish__food__variations__subtitle"
                                    >
                                        Optional
                                    </span>
                                    <div
                                        class="dish__food__variations__options"
                                        v-for="index in food.meal_addons"
                                        :key="`options__${index}`"
                                    >
                                        <div class="dfv__left">
                                            <div
                                                class="
                                                    dfv__button__outer__check
                                                "
                                            >
                                                <!-- <span
                                                    class="dfv__button"
                                                ></span> -->
                                            </div>
                                            <label class="dfv__left__title">{{
                                                index.name
                                            }}</label>
                                        </div>
                                        <div class="dfv__right">
                                            P. {{ index.price }}
                                        </div>
                                    </div>
                                </div>
                            </div>
                            <div class="dish__food__row">
                                <h2
                                    class="
                                        dish__food__instructions
                                        dish__food__miniheader
                                    "
                                >
                                    Special Instructions
                                </h2>
                                <textarea
                                    class="dish__food__special__ins"
                                    placeholder="e.g put soup in a different container"
                                />
                            </div>
                            <div>
                                <button class="dish__food__button">
                                    Add to bag
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Food",
    head() {
        return {
            title: `${this.title} | Haru`,
        };
    },
    data() {
        return { food: {}, title: "Food" };
    },
    async fetch() {
        await this.$axios
            .get(
                `https://dbresto-api.designbluemanila.com/api/frontend/branch/makati/${this.$route.params.food}`
            )
            .then((res) => {
                this.food = res.data.res;
                console.log(this.food);
                this.title = this.food.name;
            })
            .catch((err) => {
                alert("Failed to get food data");
            })
            .then(() => {
                // console.log(this.homepage);
            });
    },
};
</script>

<style>
.dfv__button__outer__check {
    height: 20px;
    width: 20px;
    margin-right: 15px;
    position: relative;
    border: 1px solid var(--background-gray);
}
.dish__food__variations__subtitle {
    color: var(--gray_2);
    font-family: Karla-Regular;
    font-size: 14px;
}
.dfv__button__outer {
    height: 20px;
    width: 20px;
    border-radius: 100px;
    margin-right: 15px;
    position: relative;
    background-color: var(--primary);
    border: 1px solid transparent;
}
.dfv__button {
    position: absolute;
    background: var(--primary);
    width: 15px;
    height: 15px;
    border: 2px solid var(--white);
    border-radius: 100px;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
.dfv__left {
    display: flex;
    align-items: center;
}
.dfv__left__title {
    margin-bottom: 0;
}
.dish__food__variations__options {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 5px 0;
    padding: 20px 0;
    transition: 0.2s ease-out;
    font-family: Karla-Bold;
    font-size: 16px;
    color: var(--black);
}
.dish__food__variations__title {
    color: var(--black);
    font-family: Karla-Bold;
    font-size: 18px;
}
.dish__food__variations {
    margin: 0px 0 10px;
    background-color: var(--white);
}
.dish__food__rotate {
    transform: rotate(90deg);
    margin-top: -2px;
}
.dish__food__symbol {
    height: 2px;
    width: 15px;
    background-color: var(--primary);
}
.dish__food__quantity__count {
    font-family: Karla-Regular;
    font-size: 25px;
    color: var(--gray_3);
    margin: 0 5px;
    min-width: 30px;
    text-align: center;
}
.dish__food__quantity__button {
    background-color: var(--light-gray);
    padding: 15px 10px;
}
.dish__food__quantity__controller {
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.dish__food__quantity:first-child {
    display: flex;
    align-items: center;
    justify-content: space-between;
    /* margin-bottom: 10px; */
}
.dish__food__special__ins {
    border: 1px solid var(--background-gray);
    border-radius: 5px;
    appearance: auto;
    resize: none;
    height: 100px;
    padding: 10px;
    font-family: Karla-Regular;
    color: var(--black);
}
.dish__food__miniheader {
    font-family: Karla-Bold;
    color: var(--black);
}
.dish__food__instructions {
    margin-bottom: 15px;
}
.dish__food__button {
    background-color: var(--primary);
    padding: 20px;
    border: none;
    border-radius: 100px;
    color: var(--white);
    font-family: Karla-Bold;
    font-size: 20px;
}
.dish__food__price {
    font-family: Karla-Regular;
    font-size: 30px;
    color: var(--primary);
}
.dish__food__description {
    font-family: Karla-Regular;
    font-size: 20px;
    color: var(--secondary);
    opacity: 0.6;
    margin: 10px 0;
}
.dish__food__h1 {
    font-family: Karla-Bold;
    font-size: 45px;
    max-width: 400px;
}
.dish__food__title {
    margin-top: 0;
    position: relative;
}
.dish__food__row {
    background-color: var(--white);
    padding: 25px 35px;
    border-radius: 15px;
    margin-bottom: 20px;
}
.left__food__img__container {
    opacity: 1;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-flow: row wrap;
    flex-direction: column;
    height: 400px;
    margin-bottom: 20px;
    border-radius: 5px;
    overflow: hidden;
}
.dish__food__right {
    min-width: 500px;
    margin: 0 10px;
}
.dish__food__left {
    margin: 0 10px;
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;
    z-index: 1;
    flex: 0 0 calc(50% - 20px);
}
.dish__food__details {
    margin: 10px px calc(8% - 20px);
    flex-flow: unset;
    display: flex;
    justify-content: center;
}
.dish__food__div {
    max-width: 1280px;
    margin: 0 auto;
}
.dish__food__inner {
    width: 100%;
    margin: 0 auto;
    overflow: hidden !important;
    max-width: unset;
    margin-bottom: 150px;
}
.dish__food__container {
    background-color: var(--light_brown);
    opacity: 1;
    padding-bottom: 50px;
    overflow: hidden;
}
</style>