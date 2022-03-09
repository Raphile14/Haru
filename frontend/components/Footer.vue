<template>
    <div id="footer">
        <div class="footer__col">
            <img
                class="footer__logo"
                src="/images/haru-logo@2x.png"
                alt="haru-logo"
            />
            <div class="footer__1">
                <h2>Follow Us</h2>
                <div class="footer__socials footer__subtitle">
                    <div>
                        <a
                            class="footer__socials__image"
                            href="https://facebook.com"
                            target="_blank"
                            ><img src="/images/socials/facebook.svg" alt="visa"
                        /></a>
                        <a
                            class="footer__socials__image"
                            href="https://instagram"
                            ><img
                                src="/images/socials/instagram.svg"
                                alt="visa"
                        /></a>
                        <a
                            class="footer__socials__image"
                            href="https://pinterest.com"
                            target="_blank"
                            ><img
                                src="/images/socials/pinterest.svg"
                                alt="visa"
                        /></a>
                    </div>
                </div>
            </div>
        </div>
        <div class="footer__col">
            <h2><strong>About</strong></h2>
            <div>
                <NuxtLink to="/our-story"> Our Story </NuxtLink>
            </div>
        </div>
        <div class="footer__col">
            <h2><strong>Extras</strong></h2>
            <div>
                <NuxtLink to="/terms-and-conditions">
                    Terms &amp; Conditions
                </NuxtLink>
                <br />
                <NuxtLink to="/privacy-policy"> Privacy Policy </NuxtLink>
            </div>
        </div>
        <div class="footer__col">
            <h2><strong>We Accept</strong></h2>
            <div>Cash on Delivery</div>
            <div class="footer__payments__container">
                <div class="payments">
                    <img
                        src="/images/payments/mastercard.png"
                        alt="mastercard"
                    />
                </div>
                <div class="payments">
                    <img src="/images/payments/visa.png" alt="visa" />
                </div>
                <div class="payments">
                    <img src="/images/payments/jcb.png" alt="jcb" />
                </div>
                <div class="payments">
                    <img src="/images/payments/gcash.svg" alt="gcash" />
                </div>
                <div class="payments">
                    <img src="/images/payments/unionpay.png" alt="unionpay" />
                </div>
            </div>
        </div>
        <div class="footer__col__2" v-on:click="scrollToTop()">
            <svg
                xmlns="http://www.w3.org/2000/svg"
                width="14.82"
                height="24"
                viewBox="0 0 14.82 24"
                class="footer__scroll"
            >
                <defs>
                    <style>
                        .a {
                            fill: #202020;
                        }
                    </style>
                </defs>
                <path
                    d="M23.41,26.93l-9.16-9.18,9.16-9.18L20.59,5.75l-12,12,12,12Z"
                    transform="translate(-8.59 -5.75)"
                    class="a"
                ></path>
            </svg>
        </div>
    </div>
</template>

<script>
export default {
    name: "Footer",
    methods: {
        async scrollToTop() {
            window.scrollTo(0, 0);
        },
    },
};
</script>

<style>
#footer {
    /* overflow: hidden;
    white-space: nowrap; */
    /* padding-left: 6em;
    padding-right: 6em;
    margin-bottom: 5em; */
    background-color: var(--white);
    display: flex;
    padding: 40px 120px;
    position: relative;
}

.footer__socials {
    display: flex;
    max-width: 200px;
}

.footer__socials__image {
    margin: 10px 5px;
}

.footer__payments__container {
    display: flex;
    flex-flow: row wrap;
    max-width: 300px;
    margin: 5px -10px;
}

.footer__col {
    flex: 0 0 25%;
}

.footer__col__2 {
    position: absolute;
    right: calc(10% - 30px);
    cursor: pointer;
}

.payments {
    background-color: var(--white);
    box-shadow: 0 3px 6px var(--box_shadow_gray);
    margin: 5px 10px;
    flex: 0 0 calc(33.33% - 20px);
    padding: 5px;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 5px;
}

.payments > img {
    max-width: 45px;
}

.footer__logo {
    max-width: 200px;
}

.footer__scroll {
    transform: rotate(90deg);
}

#footer,
#footer > div > h2 {
    font-size: 16px;
}

#footer > div,
.footer__socials,
.footer__socials > div {
    display: inline-block;
    vertical-align: text-top;
}

#footer > div {
    padding: 0.5em;
}

#footer {
    color: var(--gray_2);
}

.footer__1 {
    margin-top: 25px;
}
.footer__1 > h2 {
    font-family: Karla-Bold;
    font-size: 18px;
    color: var(--secondary);
    margin-bottom: 10px;
}

@media (max-width: 1155px) {
    .footer__container {
        padding: 40px 90px;
    }

    .footer__col:first-child {
        margin-right: 40px;
    }
}

@media (max-width: 890px) {
    .footer__container {
        padding: 40px;
    }
}

@media (max-width: 768px) {
    .footer__container {
        padding: 40px;
        flex-flow: row wrap;
    }

    .footer__col {
        margin: 10px 0;
        flex: 0 0 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
    }

    .footer__col:first-child {
        margin: unset;
    }
}
</style>
