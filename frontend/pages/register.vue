<template>
    <div class="main">
        <div class="login__container">
            <img
                class="login__img"
                src="/images/home/haru.png"
                style="height: 937px"
            />
            <div class="login__register">
                <div class="login__process">
                    <h2 class="login__header">Create an Account</h2>
                    <span class="login__description"
                        >Sign up for free and enjoy your favorite meals at
                        home.</span
                    >
                    <div class="login__wrapper">
                        <form>
                            <div class="reg__group">
                                <label for="first_name">First Name</label>
                                <input
                                    type="text"
                                    id="first_name"
                                    name="first_name"
                                    autocomplete="off"
                                    placeholder="Enter First Name"
                                    class="input_text"
                                    aria-required="true"
                                    aria-invalid="false"
                                />
                            </div>
                            <div class="reg__group">
                                <label for="last_name">Last Name</label>
                                <input
                                    type="text"
                                    id="last_name"
                                    name="last_name"
                                    autocomplete="off"
                                    placeholder="Enter Last Name"
                                    class="input_text"
                                    aria-required="true"
                                    aria-invalid="false"
                                />
                            </div>
                            <div class="reg__group">
                                <label for="email">Email Address</label>
                                <input
                                    type="email"
                                    id="email"
                                    name="email"
                                    autocomplete="off"
                                    placeholder="Enter Email"
                                    class="input_text"
                                    aria-required="true"
                                    aria-invalid="false"
                                />
                            </div>
                            <div class="reg__group">
                                <label for="contact_number"
                                    >Contact Number</label
                                >
                                <input
                                    type="text"
                                    id="contact_number"
                                    name="contact_number"
                                    autocomplete="off"
                                    placeholder="Enter Contact Number"
                                    class="input_text"
                                    aria-required="true"
                                    aria-invalid="false"
                                />
                            </div>
                            <div class="reg__group">
                                <label for="password">Password</label>
                                <input
                                    type="password"
                                    id="password"
                                    name="password"
                                    autocomplete="off"
                                    class="input_text"
                                    aria-required="true"
                                    aria-invalid="false"
                                />
                            </div>
                            <div class="reg__group">
                                <label for="confirm_password"
                                    >Confirm Password</label
                                >
                                <input
                                    type="password"
                                    id="confirm_password"
                                    name="confirm_password"
                                    autocomplete="off"
                                    class="input_text"
                                    aria-required="true"
                                    aria-invalid="false"
                                />
                            </div>
                            <div class="reg__checkbox">
                                <input
                                    type="checkbox"
                                    id="agree-terms"
                                    name="agreeTerms"
                                    value="true"
                                    class="accept_terms_condition"
                                />
                                <label for="agree-terms">
                                    I accept the
                                    <NuxtLink
                                        to="/terms-and-conditions"
                                        class="terms__button"
                                    >
                                        terms and conditions
                                    </NuxtLink>
                                </label>
                            </div>
                            <button type="submit" class="primary__button">
                                Register
                            </button>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Register",
    head() {
        return {
            title: "Register | Haru",
        };
    },
};
</script>

<style>
.terms__button {
    text-transform: none;
    font-family: Poppins-Regular;
    text-decoration: none;
    color: var(--primary);
    transition: all 0.3s ease-out;
}
.accept_terms_condition {
    width: 24px;
    height: 24px;
    border: 1px solid hsla(0, 0%, 43.9%, 0.5);
    cursor: pointer;
    margin-right: 10px;
    position: relative;
    border-radius: 5px;
    transition: 0.2s ease-in-out;
}
.reg__checkbox {
    display: flex;
    flex-flow: row wrap;
    align-items: center;
    margin-top: 15px;
    margin-bottom: 15px;
    position: relative;
}
.reg__group {
    position: relative;
    margin-bottom: 0;
    padding-bottom: 15px;
}
</style>