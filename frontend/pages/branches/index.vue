<template>
    <div class="main">
        <div class="main_container branches__container">
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
                            <span class="breadcrumb__link__active"
                                >BRANCHES</span
                            >
                        </NuxtLink>
                    </li>
                </ul>
            </div>
            <div class="branches">
                <div class="branches__inner">
                    <h2 class="branch__name">
                        <NuxtLink to="/"
                            >Makati
                            <span class="branch__title__span">
                                MAIN BRANCH
                            </span>
                        </NuxtLink>
                    </h2>
                    <p class="branch__label">
                        <span class="branch__icon branch__address" />
                        <a
                            href="http://maps.google.com/?q=37 Polaris, Makati, 1209 Metro Manila"
                            class="branch__subtitle"
                            target="_blank"
                            >37 Polaris, Makati, 1209 Metro Manila</a
                        >
                    </p>
                    <p class="branch__label">
                        <span class="branch__icon branch__phone" />
                        <a href="tel:09952781800" class="branch__subtitle"
                            >09952781800</a
                        >
                    </p>
                    <p class="branch__label">
                        <span class="branch__icon branch__time" />
                        11:00 am - 10:00 pm
                    </p>
                </div>
            </div>
        </div>
        <div class="">
            <iframe
                class="branches__map"
                src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d30894.418157718457!2d121.01097272406123!3d14.553297052384632!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3397c9aa7a53211d%3A0xb0c17febc350de14!2s37%20Polaris%2C%20Makati%2C%201209%20Metro%20Manila!5e0!3m2!1sen!2sph!4v1647227969915!5m2!1sen!2sph"
                width="600"
                height="450"
                style="border: 0"
                allowfullscreen=""
                loading="lazy"
            ></iframe>
        </div>
    </div>
</template>

<script>
export default {
    name: "Branches",
    head() {
        return {
            title: "Branches | Haru",
        };
    },
};
</script>

<style>
.branches {
    display: flex;
    flex-flow: row wrap;
    margin-left: -10px;
    margin-right: -10px;
}
.branches__inner {
    padding: 24px 33px;
    background-color: #fff;
    border: 1px solid #e6e6e6;
    border-radius: 10px;
    flex: 0 0 calc(50% - 20px);
    margin: 10px;
}
.branch__name {
    font-size: 18px;
    text-transform: none;
    font-family: Poppins-Regular;
    color: #ff6f00;
}
.branch__title__span {
    background: #888;
    color: #fff;
    padding: 1px 6px;
    border-radius: 4px;
    font-size: 10px;
    text-transform: uppercase;
    margin-left: 6px;
    position: relative;
    top: -2px;
}
.branch__label {
    font-size: 16px;
    text-transform: none;
    font-family: Poppins-Regular;
    color: #383838;
    margin: 10px 0;
    padding-left: 32px;
    position: relative;
}
.branch__label:last-child {
    margin-bottom: 0;
}
.branch__icon {
    position: absolute;
    left: 0;
    top: 0;
    bottom: 0;
    background-repeat: no-repeat;
    background-size: contain;
    background-position: left 3px;
    width: 20px;
}
.branch__time {
    background-image: url("/icons/time.svg");
}
.branch__phone {
    background-image: url("/icons/phone.svg");
}
.branch__address {
    background-image: url("/icons/home.svg");
}
.branch__subtitle {
    text-decoration: none;
    color: #888;
}
.branches__map {
    width: 100%;
    height: 520px;
    margin: 20px 0 0;
}
</style>