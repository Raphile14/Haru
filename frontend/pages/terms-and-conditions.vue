<template>
    <div class="main">
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
                        <NuxtLink
                            to="/terms-and-conditions"
                            class="breadcrumb__link"
                        >
                            <span class="breadcrumb__link__active"
                                >TERMS AND CONDITIONS</span
                            >
                        </NuxtLink>
                    </li>
                </ul>
            </div>
        </div>
        <div class="terms__container">
            <h1 class="terms__title">Terms and Conditions</h1>
            <div class="terms__content">
                <p>
                    Welcome to our website www.janggarae.com ("Site"). These
                    Terms of Use govern your access and use of the Site. The
                    Access and the use of the Site, as well as the purchase of
                    products on www.janggarae.com, are based on the assumption
                    that you have read, understood and accepted these Conditions
                    of Use. This Site is managed and maintained by Eurostep Srl
                    VAT ID no. 03896260241 and Eurostep Commerce Srl VAT ID no.
                    04887580266 (hereinafter reffered indifferently to as
                    "Manager"), both with legal head office in Italy, Via
                    Feltrina Sud, 192 - 31044 Montebelluna (TV).
                </p>
                <p>
                    If you need help, you can visit Customer Service area. You
                    will find information on orders, shipping, refunds and
                    returns of products purchased on the Site, a registration,
                    tips and other general information on the services provided.
                    You can contact us by e-mail to: customercare@janggarae.com.
                </p>
                <p>
                    For further legal information, please visit sections General
                    Terms of Sale and Conditions of Use and Privacy Policy on
                    the Site. The Manager may amend or simply update, in whole
                    or in part, these Conditions of Use. Therefore, the User
                    should regularly access this section to check the
                    publication of the latest and updated Conditions of Use. If
                    he/her does not agree, in whole or in part with the
                    Conditions of Use, please do not use our website.
                </p>
                <p>
                    The access and the use of the Site, including display of web
                    pages, communication with the Manager, the ability to
                    download product information and making purchases on the
                    website, are carried out by our Users exclusively for
                    personal purposes, which should in no way be connected to
                    any trade, business and professional activities. The User is
                    the solely liable for the use of the Site and its contents.
                    The Manager, in fact, can not be held responsible for any
                    use not in compliance with applicable laws, the web site and
                    its contents by any of its Users, prejudice to the
                    responsibility of the Manager for willful misconduct and
                    gross negligence. In particular, it will be the one and only
                    responsible for the communication of information and
                    incorrect data, or false about third parties, although they
                    have given their consent, and in consideration of the
                    improper use of themselves.
                </p>
                <p>
                    Finally, since each material will be downloaded or otherwise
                    obtained by using at the User’s choice and risk, all
                    liability for any damage to computer systems or data loss
                    resulting from unloading falls on the User and may not be
                    attributed to the Manager. The Manager accepts no
                    responsibility for any damages resulting inaccessibility to
                    services on site or from damage caused by viruses, corrupted
                    files, errors, omissions, service interruptions, deletions
                    of content, network problems, providers or telephone
                    connections and / or data transmission, unauthorized access
                    to, alteration of data, failure and / or malfunction of
                    electronic equipment itself.
                </p>
                <p>
                    You are responsible for the safekeeping and proper use of
                    personal information, including credentials that allow
                    access to confidential services, as well as for any damages
                    or injury which might arise against the Manager or third
                    parties as a result of misuse, loss, theft of such
                    information.
                </p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "TermsAndConditions",
    head() {
        return {
            title: "Terms and Conditions | Haru",
        };
    },
};
</script>

<style>
.terms__container {
    padding: 50px 0;
    width: 100%;
    max-width: 65%;
    margin: 0 auto;
}
.terms__title {
    font-size: 40px;
}
.terms__content {
    padding: 20px 0 70px;
    padding-bottom: 20px;
}
.terms__content > p {
    font-size: 16px;
    text-transform: none;
    font-family: Poppins-Light;
    color: #525252;
    margin-bottom: 1.5em;
}
</style>