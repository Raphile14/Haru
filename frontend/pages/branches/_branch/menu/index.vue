<template>
    <div class="main">
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
                                <span class="breadcrumb__link__active"
                                    >MENU</span
                                >
                            </NuxtLink>
                        </li>
                    </ul>
                </div>
                <div class="menu__categories">
                    <div class="menu__wrapper">
                        <div
                            class="menu__category"
                            v-for="index in filteredMenu"
                            :key="`menu__${index.id}`"
                        >
                            <div class="menu__title">{{ index.name }}</div>
                        </div>
                    </div>
                </div>
            </div>
            <div
                class="indiv__category"
                v-for="index in filteredMenu"
                :key="`indiv__${index.id}`"
            >
                <div class="indiv__header">
                    <div>
                        <h2 class="indiv__title">{{ index.name }}</h2>
                    </div>
                    <div>
                        <p class="indiv__description">
                            {{ index.description }}
                        </p>
                    </div>
                </div>
                <div class="indiv__food__container">
                    <Dish
                        class="indiv__dish"
                        v-for="food in index.product"
                        :key="food.id"
                        :dish="food"
                    />
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    // components: { Dish },
    name: "Menu",
    head() {
        return {
            title: "Makati Menu | Haru",
        };
    },
    data() {
        return { menu: {}, filteredMenu: [] };
    },
    async fetch() {
        // Get Makati Homepage Data
        await this.$axios
            .get(
                "https://dbresto-api.designbluemanila.com/api/frontend/branch/makati/menu"
            )
            .then((res) => {
                this.menu = res.data.data;

                // Filter menu
                for (let x = 0; x < this.menu.length; x++) {
                    console.log(x);
                    if (this.menu[x].product.length > 0) {
                        this.filteredMenu.push(this.menu[x]);
                    }
                }
                console.log(this.menu.length);
            })
            .catch((err) => {
                console.log(err);
                alert("Failed to get menu data");
            })
            .then(() => {
                // console.log(this.homepage);
            });
    },
};
</script>

<style>
.indiv__food__container {
    display: flex;
    flex-flow: row wrap;
    margin: 0 calc(8% - 30px);
}
.indiv__description {
    font-family: Karla-Regular;
    font-size: 25px;
    color: var(--secondary);
    opacity: 0.6;
    margin-top: 0;
    margin-bottom: 0;
}
.indiv__title {
    color: var(--text_dark_primary);
    font-family: Karla-Bold;
    font-size: 50px;
    margin-top: 0;
    margin-bottom: 0;
}
.indiv__header {
    opacity: 1;
    padding: 0 calc(7% - 10px) 40px;
}
.indiv__category {
    padding: 0 0 50px;
    opacity: 1;
}
.menu__title {
    font-family: Karla-Bold;
    color: #383838;
    white-space: nowrap;
    font-size: 22px;
}
.menu__category {
    position: relative;
    padding: 10px 30px;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 100px;
    background-color: #e8e8e8;
    margin: 0 5px;
    transition: 0.2s ease-in-out;
}
.menu__wrapper {
    display: flex;
    overflow-x: hidden;
}
.menu__categories {
    padding: 50px 0 10px;
    overflow-x: auto;
}
</style>