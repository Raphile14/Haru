<template>
    <div id="navbar" data-v-58dab166="" data-v-0f60d5c4="">
        <div class="wrapper" data-v-58dab166="">
            <div class="left" data-v-58dab166="">
                <a
                    href="/"
                    rel="canonical"
                    class="logo nuxt-link-exact-active nuxt-link-active"
                    data-v-58dab166=""
                    aria-current="page"
                    ><img
                        data-v-58dab166=""
                        src="https://dbresto-api.designbluemanila.com/storage/uploads/2021-11-22/08-23-04-915237/haru-logo@2x.png"
                        alt="Haru"
                        class="logo"
                /></a>
                <ul class="list desktop_list" data-v-58dab166="">
                    <li data-v-58dab166="">
                        <a
                            href="/branches/makati/menu"
                            rel="canonical"
                            class="item"
                            data-v-58dab166=""
                            >Menu</a
                        >
                    </li>
                    <li data-v-58dab166="">
                        <a
                            href="/track-my-order"
                            rel="canonical"
                            class="item"
                            data-v-58dab166=""
                            >Track My Order</a
                        >
                    </li>
                </ul>
            </div>
            <div class="right" data-v-58dab166="">
                <div class="desktop" data-v-58dab166="">
                    <div
                        data-v-58dab166=""
                        id="branches"
                        class="dropdown pointer"
                    >
                        <div data-v-58dab166="" class="selected">Makati</div>
                        <!---->
                    </div>
                    <div id="default_form" data-v-58dab166="">
                        <form class="form_search" data-v-58dab166="">
                            <div class="form_group input" data-v-58dab166="">
                                <input
                                    type="text"
                                    name="searchKeyword"
                                    autocomplete="off"
                                    placeholder="Search"
                                    value=""
                                    class="default_input global_search"
                                    data-v-58dab166=""
                                />
                            </div>
                            <button
                                type="button"
                                class="submit"
                                style="cursor: default"
                                data-v-58dab166=""
                            >
                                <i
                                    class="icon-search"
                                    style="font-size: 18px"
                                    data-v-58dab166=""
                                ></i>
                            </button>
                        </form>
                    </div>
                    <a href="/login" class="login pointer" data-v-58dab166=""
                        >Login</a
                    >
                    <!---->
                    <!---->
                    <a href="#" class="cart" data-v-58dab166=""
                        ><div class="icon" data-v-58dab166="">
                            <img
                                src="/icons/cart.png"
                                class="shopping_cart"
                                data-v-58dab166=""
                            />
                            <div class="number" data-v-58dab166="">
                                <span data-v-58dab166="">0</span>
                            </div>
                        </div></a
                    >
                </div>
                <div class="mobile" data-v-58dab166="">
                    <a to="#" class="cart" data-v-58dab166=""
                        ><div class="icon" data-v-58dab166="">
                            <img
                                src="/icons/cart.png"
                                class="shopping_cart cart_mobile"
                                data-v-58dab166=""
                            />
                            <div class="number" data-v-58dab166="">
                                <span data-v-58dab166="">0</span>
                            </div>
                        </div></a
                    >
                    <div class="burger" data-v-58dab166="">
                        <div class="bar top" data-v-58dab166=""></div>
                        <div class="bar middle" data-v-58dab166=""></div>
                        <div class="bar bottom" data-v-58dab166=""></div>
                    </div>
                </div>
            </div>
        </div>
        <!---->
        <!---->
    </div>
    <!-- <nav id="navbar">
        <div class="wrapper">
            <div class="left__align">
                <div>
                    <NuxtLink to="/">
                        <img
                            class="navbar__logo"
                            src="/images/haru-logo@2x.png"
                            alt="haru-logo"
                        />
                    </NuxtLink>
                </div>

                <div>
                    <NuxtLink to="/branches/makati/menu"> Menu </NuxtLink>
                    <NuxtLink to="/track-my-order"> Track My Order </NuxtLink>
                </div>
            </div>

            <div class="right__align">
                <img
                    class="navbar__cart right__align"
                    src="/images/cart.png"
                    alt="cart"
                />
                <NuxtLink to="/login" class="right__align">
                    <button class="login">Login</button>
                </NuxtLink>
                <input
                    class="right__align"
                    type="text"
                    name=""
                    id=""
                    placeholder="Search"
                />
                <select name="" id="" class="right__align">
                    <option
                        v-for="index in branches"
                        :key="`branch_${index.id}`"
                    >
                        {{ index.name }}
                    </option>
                </select>
            </div>
        </div>
    </nav> -->
</template>

<script>
export default {
    name: "NavBar",
    props: {
        branches: {
            type: Object / Array,
            default: null,
        },
    },
};
</script>

<style>
#navbar {
    background-color: var(--white);
    box-shadow: 0 3px 3px rgb(86 44 10 / 19%);
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    width: 100%;
    z-index: 999;
}

#navbar .wrapper {
    display: flex;
    justify-content: space-between;
    flex-flow: row wrap;
    align-items: center;
    padding: 20px 95px;
}

/* Left */
#navbar .wrapper .left {
    display: flex;
    position: relative;
    z-index: 3;
}

#navbar .wrapper .left .logo {
    display: block;
    flex: 0 0 300px;
    max-width: 130px;
    padding: 0;
    display: flex;
    justify-content: center;
}

#navbar .wrapper .left .list {
    display: flex;
    align-items: center;
    flex: 0 0 100%;
    padding: 0;
    margin-left: 35px;
}

#navbar .wrapper .right {
    display: flex;
    align-items: center;
    justify-content: flex-end;
    position: relative;
    z-index: 2;
}

#navbar .wrapper .left .list li {
    list-style: none;
    margin: 0 13px;
}

/* Right */
#navbar .wrapper .right .desktop {
    display: flex;
    align-items: center;
    justify-content: space-between;
}

#navbar .wrapper .dropdown {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    border-radius: 5px;
    background-color: var(--background-primary);
    text-align: center;
    cursor: pointer;
    padding: 7px 10px;
    position: relative;
    margin: 0;
    max-width: 100%;
    border: 1px solid transparent;
    font-size: 16px;
    text-transform: none;
    font-family: Poppins-Regular;
    font-family: Karla-Regular;
    font-size: 18px;
    color: #f2e8da;
    width: 220px;
}

#navbar .wrapper #default_form {
    width: 100%;
    max-width: 195px;
    margin: 0 10px;
}

#navbar .wrapper .right #default_form .form_search[data-v-58dab166] {
    transition: all 0.3s ease-out;
}
#navbar .wrapper #default_form .form_search {
    display: flex;
    align-items: center;
    height: 100%;
    border-radius: 5px;
    border: 1px solid #dedede;
    padding: 8px;
    position: relative;
}

#navbar .wrapper #default_form .form_search button {
    padding: 0;
    width: 35px;
}
button,
input,
select,
textarea {
    -webkit-appearance: none;
    background-color: transparent;
    box-shadow: none;
    outline: none;
    border: none;
    width: 100%;
}

#navbar .wrapper #default_form .form_search input {
    color: #666;
    font-size: 16px;
    font-family: Karla-Regular;
}

/* Icon search */
#navbar .wrapper .right #default_form .form_search i[data-v-58dab166] {
    color: #dedede !important;
    transition: all 0.3s ease-out;
}
[class^="icon-"],
[class*=" icon-"] {
    display: inline;
    width: auto;
    height: auto;
    line-height: normal;
    vertical-align: baseline;
    background-image: none;
    background-position: 0% 0%;
    background-repeat: repeat;
    margin-top: 0;
}

[class^="icon-"],
[class*=" icon-"] {
    font-family: FontAwesome;
    font-weight: normal;
    font-style: normal;
    text-decoration: inherit;
    -webkit-font-smoothing: antialiased;
    *margin-right: 0.3em;
}

/* Login */
#navbar .wrapper .login {
    font-family: Karla-Regular;
    color: #f2e8da;
    border-radius: 5px;
    margin: 0 5px;
    background-color: var(--white);
    text-align: center;
    display: flex;
    align-self: center;
    padding: 7px 30px;
    transition: all 0.3s ease-out;
    color: var(--text-primary);
    border: 1px solid var(--primary);
}

#navbar .wrapper .right a {
    margin: 0 12px;
}

/* Cart */
#navbar .wrapper .cart {
    justify-content: center;
    margin: 0 12px;
    cursor: pointer;
}

#navbar .wrapper .cart,
#navbar .wrapper .cart .icon {
    position: relative;
    display: flex;
    align-items: center;
}

#navbar .wrapper .right a {
    margin: 0 12px;
}

#navbar .wrapper .cart .icon .shopping_cart {
    width: 25px;
}

#navbar .wrapper .cart {
    justify-content: center;
    margin: 0 12px;
    cursor: pointer;
}

#navbar .wrapper .cart,
#navbar .wrapper .cart .icon {
    position: relative;
    display: flex;
    align-items: center;
}

#navbar .wrapper .cart,
#navbar .wrapper .cart .icon {
    position: relative;
    display: flex;
    align-items: center;
}

/* Number */
#navbar .wrapper .cart .icon .number {
    position: absolute;
    bottom: 52%;
    left: 70%;
    background-color: var(--background-primary);
    height: 22px;
    width: 22px;
    text-align: center;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
}

#navbar .wrapper .cart .icon .number span {
    margin: 0;
    padding: 0;
    font-size: 9px;
    text-transform: none;
    font-family: Poppins-Regular;
    color: #fff;
    position: relative;
    top: 1px;
}

ul {
    padding: 0;
    list-style-type: none;
}

/* Burger */
#navbar .wrapper .burger {
    flex: 0 0 25px;
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    flex-direction: column;
    height: 18px;
}

#navbar .wrapper .burger .bar {
    width: 100%;
    height: 2px;
    margin-top: 6px;
    background-color: #383838;
    transform: rotate(0deg);
    transition: 0.3s ease-in-out;
}

#navbar .wrapper .burger .bar:first-child {
    margin-top: 0;
}

#navbar .wrapper .burger .bar {
    width: 100%;
    height: 2px;
    margin-top: 6px;
    background-color: #383838;
    transform: rotate(0deg);
    transition: 0.3s ease-in-out;
}

#navbar .wrapper .burger .bar {
    width: 100%;
    height: 2px;
    margin-top: 6px;
    background-color: #383838;
    transform: rotate(0deg);
    transition: 0.3s ease-in-out;
}

@media (max-width: 1280px) {
    #navbar .wrapper {
        padding: 20px 5%;
    }
    #navbar .wrapper .left .logo[data-v-58dab166] {
        flex: 0 0 130px;
    }

    #navbar .wrapper .left .list[data-v-58dab166] {
        padding: 0;
    }

    #navbar .wrapper .right .cart .icon img[data-v-58dab166] {
        width: 25px;
    }

    #navbar .wrapper .right .cart .icon .number[data-v-58dab166] {
        height: 20px;
        width: 20px;
    }

    #navbar .wrapper .right .cart .icon img[data-v-58dab166] {
        width: 25px;
    }

    #navbar .wrapper .right .cart .icon img.cart_mobile[data-v-58dab166] {
        width: 45px;
        margin: 0;
        padding: 0;
    }
}
@media (max-width: 1225px) {
    #navbar .wrapper {
        padding: 20px 55px;
    }
}
@media (max-width: 1167px) {
    #navbar .wrapper {
        padding: 20px 65px;
    }
}

@media (max-width: 1080px) {
    #navbar .wrapper .left .logo[data-v-58dab166] {
        flex: 0 0 170px;
        background-size: contain;
    }

    #navbar .wrapper .left .list[data-v-58dab166] {
        margin-left: 20px;
    }

    #navbar .wrapper .left .list li[data-v-58dab166] {
        margin: 0 10px;
    }

    #navbar .wrapper .right #default_form .form_search button[data-v-58dab166] {
        padding: 0;
    }

    #navbar .wrapper .right #default_form .form_search input[data-v-58dab166] {
        font-size: 14px;
        opacity: 0.5;
    }

    #navbar .wrapper .right .login[data-v-58dab166] {
        padding: 8px 40px;
    }

    #navbar .wrapper .right .cart[data-v-58dab166] {
        position: relative;
        display: flex;
        align-items: center;
        justify-content: center;
        margin: 0 5px;
    }

    #navbar .wrapper .right .cart img[data-v-58dab166] {
        width: 80px;
    }

    #navbar .wrapper .right .cart .number[data-v-58dab166] {
        position: absolute;
        top: 0;
        right: 0;
        background-color: #ff6f00;
        padding: 10px;
        border-radius: 50%;
        margin-top: -10px;
    }

    #navbar .wrapper .right .cart[data-v-58dab166] {
        position: relative;
        display: flex;
        align-items: center;
        justify-content: center;
        margin: 0 5px;
    }

    #navbar .wrapper .right .cart img[data-v-58dab166] {
        width: 80px;
    }
}

@media (max-width: 1030px) {
    #navbar .wrapper[data-v-58dab166] {
        padding: 20px calc(5% - 20px);
    }

    #navbar .wrapper .left .desktop_list[data-v-58dab166],
    #navbar .wrapper .right .desktop[data-v-58dab166] {
        display: none;
    }

    #navbar .wrapper .left .desktop_list[data-v-58dab166],
    #navbar .wrapper .right .desktop[data-v-58dab166] {
        display: none;
    }

    #navbar .wrapper .right .mobile[data-v-58dab166] {
        display: flex !important;
        align-items: center;
        justify-content: flex-end;
    }

    #navbar .wrapper .right .cart[data-v-58dab166] {
        margin: 0 25px;
    }

    #navbar .wrapper .right .mobile[data-v-58dab166] {
        display: flex !important;
        align-items: center;
        justify-content: flex-end;
    }

    #navbar .wrapper .right .cart[data-v-58dab166] {
        margin: 0 25px;
    }
}

@media (max-width: 950px) and (min-width: 300px) {
    #navbar .wrapper[data-v-58dab166] {
        padding: 15px 0;
        max-width: 90%;
        margin: 0 auto;
    }

    #navbar .wrapper .left .logo[data-v-58dab166] {
        flex: 0 0 105px;
    }

    #navbar .wrapper .left .list[data-v-58dab166] {
        display: none;
    }

    #navbar .wrapper .left .list li[data-v-58dab166] {
        margin: 0 8px;
    }

    #navbar .wrapper .right .desktop[data-v-58dab166] {
        display: none;
    }

    #navbar .wrapper .right .mobile[data-v-58dab166] {
        display: flex;
        align-items: center;
        justify-content: flex-end;
    }

    #navbar .wrapper .right .mobile[data-v-58dab166] {
        display: flex;
        align-items: center;
        justify-content: flex-end;
    }

    #navbar .wrapper .right .mobile .cart[data-v-58dab166] {
        margin: 0;
        padding: 0 15px 0 5px;
    }

    #navbar .wrapper .right .mobile .cart .icon[data-v-58dab166] {
        display: flex;
        align-items: center;
    }

    #navbar .wrapper .right .mobile .cart .icon .number[data-v-58dab166] {
        padding: 7px;
        height: 7px;
        width: 7px;
    }
}

/* #navbar {
    overflow: hidden;
    white-space: nowrap;
    padding-left: 5em;
    padding-right: 5em;
    background-color: var(--white);
    box-shadow: 0 3px 3px rgb(86 44 10 / 19%);
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    width: 100%;
    z-index: 999;
}

.wrapper {
    padding: 15px 0;
    vertical-align: middle;
    display: flex;
    justify-content: space-between;
    flex-flow: row wrap;
    align-items: center;
}

#navbar > div > div,
#navbar > div > div > div,
.right__align {
    display: inline-block;
}

.navbar__logo,
.left__align {
    display: block;
    flex: 0 0 300px;
    max-width: 130px;
    padding: 0;
    display: flex;
    justify-content: center;
}

.left__align {
    float: left;
}

.right__align {
    float: right;
}

.login {
    font-family: "Karla-Regular", sans-serif;
    border-radius: 5px;
    background-color: var(--white);
    text-align: center;
    display: flex;
    align-self: center;
    padding: 7px 30px;
    transition: all 0.3s ease-out;
    color: var(--text-primary);
    border: 1px px solid var(--primary);
}

@media (max-width: 1280px) {
    #navbar .left__align .navbar__logo {
        flex: 0 0 130px;
    }
}
@media (max-width: 1080px) {
    #navbar .left__align .navbar__logo {
        flex: 0 0 170px;
        background-size: contain;
    }
}
@media (max-width: 950px) and (min-width: 300px) {
    #navbar .left__align .navbar__logo {
        flex: 0 0 105px;
    }
} */
</style>