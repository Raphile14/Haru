<template>
    <div id="footer">
        <div>
            <img src="/images/haru-logo@2x.png" alt="haru-logo" />
            <h2><strong>Follow Us</strong></h2>
            <div class="footer__socials footer__subtitle">
                <div><img src="/images/socials/facebook.svg" alt="visa" /></div>
                <div>
                    <img src="/images/socials/instagram.svg" alt="visa" />
                </div>
                <div>
                    <img src="/images/socials/pinterest.svg" alt="visa" />
                </div>
            </div>
        </div>
        <div>
            <h2><strong>About</strong></h2>
            <div>
                <NuxtLink to="/our-story"> Our Story </NuxtLink>
            </div>
        </div>
        <div>
            <h2><strong>Extras</strong></h2>
            <div>
                <NuxtLink to="/terms-and-conditions">
                    Terms &amp; Conditions
                </NuxtLink>
                <NuxtLink to="/privacy-policy"> Privacy Policy </NuxtLink>
            </div>
        </div>
        <div>
            <h2><strong>We Accept</strong></h2>
            <div>Cash on Delivery</div>
            <div class="payments">
                <div>
                    <img
                        src="/images/payments/mastercard.png"
                        alt="mastercard"
                    />
                </div>
                <div>
                    <img src="/images/payments/visa.png" alt="visa" />
                </div>
                <div>
                    <img src="/images/payments/jcb.png" alt="jcb" />
                </div>
                <div>
                    <img src="/images/payments/gcash.svg" alt="gcash" />
                </div>
                <div>
                    <img src="/images/payments/unionpay.png" alt="unionpay" />
                </div>
            </div>
        </div>
        <div>Scroll Up</div>
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
    padding-left: 5em;
    padding-right: 5em;
}

#footer,
#footer > div > h2 {
    font-size: 16px;
}

#footer > div,
.footer__socials {
    display: inline-block;
    vertical-align: text-top;
}

#footer > div {
    padding: 0.5em;
}

#footer {
    color: var(--gray_2);
}
</style>