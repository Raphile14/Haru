<template>
    <nav id="navbar">
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
    
                <!-- Left Links -->
                <div>
                    <NuxtLink to="/branches/makati/menu"> Menu </NuxtLink>
                    <NuxtLink to="/track-my-order"> Track My Order </NuxtLink>
                </div>
            </div>
    
            <!-- Right Links -->
            <div class="right__align">
                <select name="" id="">
                    <option value="Makati">Makati</option>
                </select>
                <input type="text" name="" id="" placeholder="Search" />
                <NuxtLink to="/login">
                    <button type="button">Login</button>
                </NuxtLink>
                <img class="navbar__cart" src="/images/cart.png" alt="cart" />
            </div>
        </div>
    </nav>
</template>

<script>
export default {
    name: "NavBar",
};
</script>

<style>
#navbar {
    overflow: hidden;
    white-space: nowrap;
    padding-bottom: 1em;
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
}

#navbar > div > div,
#navbar > div > div > div {
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

/* Media Queries */
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
}
</style>