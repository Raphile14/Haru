<template>
    <div id="footer">
        <div class="footer__container">
            <div class="footer__col">
                <img
                    class="footer__logo"
                    src="/images/haru-logo@2x.png"
                    alt="haru-logo"
                />
                <h2><strong>Follow Us</strong></h2>
                <div class="footer__socials footer__subtitle">
                    <div>
                        <img src="/images/socials/facebook.svg" alt="visa" />
                    </div>
                    <div>
                        <img src="/images/socials/instagram.svg" alt="visa" />
                    </div>
                    <div>
                        <img src="/images/socials/pinterest.svg" alt="visa" />
                    </div>
                </div>
            </div>
        </div>
        <div class="">
            <h2><strong>About</strong></h2>
            <div>
                <NuxtLink to="/our-story"> Our Story </NuxtLink>
            </div>
        </div>
        <div class="">
            <h2><strong>Extras</strong></h2>
            <div>
                <NuxtLink to="/terms-and-conditions">
                    Terms &amp; Conditions
                </NuxtLink>
                <br />
                <NuxtLink to="/privacy-policy"> Privacy Policy </NuxtLink>
            </div>
        </div>
        <div class="">
            <h2><strong>We Accept</strong></h2>
            <div>Cash on Delivery</div>
            <div>
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
        <div class="footer__col">
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
};
</script>

<style>
#footer {
    overflow: hidden;
    white-space: nowrap;
    padding-left: 6em;
    padding-right: 6em;
    margin-bottom: 5em;
    background-color: var(--white);
}

.footer__container {
    display: flex;
    padding: 40px 120px;
    position: relative;
}

.footer__col {
    flex: 0 0 25%;
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
.payments,
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
