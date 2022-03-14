<template>
    <div class="main main_container">
        <div id="breadcrumb">
            <ul>
                <li>
                    <NuxtLink to="/" class="breadcrumb__link"> HOME </NuxtLink>
                    <span class="slash"> / </span>
                </li>
                <li>
                    <NuxtLink to="/search" class="breadcrumb__link">
                        SEARCH
                    </NuxtLink>
                    <span class="slash"> / </span>
                </li>
                <li>
                    <NuxtLink to="/" class="breadcrumb__link">
                        <span class="breadcrumb__link__active">{{
                            $route.params.query
                        }}</span>
                    </NuxtLink>
                </li>
            </ul>
        </div>
        <div>
            <div class="search__form">
                <h2 class="search__title">Search</h2>
                <form v-on:submit.prevent="submit($event)">
                    <input
                        type="text"
                        v-model="keyword"
                        class="search__input"
                        placeholder="Search"
                    />
                </form>
            </div>
            <div class="search__results">
                <div v-if="data.length == 0" class="search__no">
                    <div class="search__inner">
                        <img
                            src="/icons/no_search_result.svg"
                            class="search__img__no"
                        />
                        <div>
                            <h2 class="search__no__result__message">
                                Sorry, we couldn't find any search results for
                                '{{ $route.params.query }}'
                            </h2>
                        </div>
                    </div>
                </div>
                <div v-else class="search__no">
                    <div class="search__food__container">
                        <Dish
                            class="search__food__item"
                            v-for="index in data"
                            :key="index.id"
                            :dish="index"
                        />
                    </div>
                    <div class="search__pagination__container">
                        <p class="pagination_stats">
                            Showing <span>{{ food.from }}</span> to
                            <span>{{ food.to }}</span> of
                            <span>{{ food.total }}</span> entries
                        </p>
                        <div
                            class="pagination__pages"
                            v-if="food.last_page > 1"
                        >
                            <!-- Prev button -->
                            <div
                                :class="{
                                    search__button: food.current_page > 1,
                                    search__disabled: food.current_page == 1,
                                }"
                                @click="search(food.prev_page_url)"
                            >
                                &lt;
                            </div>

                            <!-- First page -->
                            <div
                                :class="{
                                    search__number: food.current_page != 1,
                                    search__active: food.current_page == 1,
                                }"
                                @click="search(food.first_page_url)"
                            >
                                1
                            </div>

                            <!-- Search Numbers -->
                            <!-- <div
                                class="search__separator"
                                v-if="food.current_page - 1 > 4"
                            >
                                . . .
                            </div> -->

                            <div
                                :key="`page__${pageNum}`"
                                v-for="pageNum in pages"
                                :class="{
                                    search__number:
                                        food.current_page != pageNum,
                                    search__active:
                                        food.current_page == pageNum,
                                }"
                                @click="search(food.links[pageNum].url)"
                            >
                                {{ pageNum }}
                            </div>

                            <!-- <div
                                class="search__separator"
                                v-if="food.last_page - food.current_page > 4"
                            >
                                . . .
                            </div> -->

                            <!-- Last Page -->
                            <div
                                :class="{
                                    search__number:
                                        food.current_page != food.last_page,
                                    search__active:
                                        food.current_page == food.last_page,
                                }"
                                @click="search(food.last_page_url)"
                            >
                                {{ food.last_page }}
                            </div>

                            <!-- Next button -->
                            <div
                                :class="{
                                    search__button:
                                        food.current_page < food.last_page,
                                    search__disabled:
                                        food.current_page == food.last_page,
                                }"
                                @click="search(food.next_page_url)"
                            >
                                &gt;
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
    name: "SearchQuery",
    head() {
        return {
            title: "Search Results | Haru",
        };
    },
    data() {
        return {
            keyword: "",
            food: {},
            data: [],
            pages: [],
        };
    },
    created() {
        this.search();
    },
    methods: {
        async submit(e) {
            this.$router.push(`/search/${this.keyword}`);
        },
        async search(pageUrl) {
            let url =
                "https://dbresto-api.designbluemanila.com/api/product/search";
            if (pageUrl) {
                url = pageUrl;
            }
            await this.$axios({
                method: "post",
                url: `${url}`,
                data: {
                    searchKeyword: this.$route.params.query,
                    branch: 21,
                },
            })
                .then((res) => {
                    this.data = res.data.data.data;
                    this.food = res.data.data;
                    this.pages = [];
                    for (let x = 2; x < this.food.last_page; x++) {
                        this.pages.push(x);
                    }
                })
                .catch((err) => {
                    console.log(err);
                    alert("Failed to obtain data");
                });
        },
    },
    async fetch() {
        this.search();
    },
};
</script>

<style>
.search__form {
    margin-top: 0;
}
.search__title {
    font-family: Karla-Bold;
    font-size: 45px;
    color: var(--secondary);
    margin-top: 0;
    margin-bottom: 0;
}
.search__input {
    border: 1px solid var(--gray_2);
    padding: 10px;
    border-radius: 5px;
}
.search__no {
    padding: 0 0 50px;
    opacity: 1;
}
.search__inner {
    opacity: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 0 calc(15% - 20px);
    margin-top: 70px;
}
.search__results {
    margin-top: 1em;
}
.search__img__no {
    max-width: 150px;
    margin-bottom: 25px;
}
.search__no__result__message {
    font-family: Karla-Bold;
    text-align: center;
    font-size: 30px;
    margin-bottom: 10px;
    max-width: 500px;
}
.search__food__container {
    display: flex;
    flex-flow: row wrap;
    margin: 0 calc(8% - 30px);
}
.search__food__item {
    opacity: 1;
    flex: 0 0 calc(25% - 20px);
    margin: 10px;
}
.search__pagination__container {
    margin: 3em calc(8% - 20px);
}
.pagination_stats {
    font-family: Karla-Regular;
    font-size: 18px;
}
.pagination__pages {
    display: flex;
    flex-flow: row wrap;
    align-items: center;
    justify-content: center;
    padding: 20px 0 30px;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
}
.search__active {
    pointer-events: none;
    background-color: #fce8e7;
    color: #da2519;
    border: 1px solid #da2519;
    border-radius: 4px;
    padding: 8px 14px;
    cursor: pointer;
    transition: 0.3s ease-in-out;
    margin: 0 3px 10px;
}
.search__number {
    color: #da2519;
    background-color: transparent;
    border: 1px solid #da2519;
    border-radius: 4px;
    padding: 8px 14px;
    cursor: pointer;
    transition: 0.3s ease-in-out;
    margin: 0 3px 10px;
}
.search__separator {
    color: var(--primary);
    padding: 0 5px;
}
.search__disabled {
    background-color: #e2e2e2;
    cursor: default;
    border: 1px solid #e2e2e2;
    border-radius: 4px;
    transition: 0.3s ease-in-out;
    padding: 8px 14px;
    margin: 0 3px 10px;
}
.search__button {
    background-color: var(--background-primary);
    border: 1px solid var(--primary);
    border-radius: 4px;
    padding: 8px 14px;
    cursor: pointer;
    transition: 0.3s ease-in-out;
    margin: 0 3px 10px;
}
</style>