<template>
    <div class="main">
        <div class="forgot__password__page">
            <div class="forgot__password__main__container">
                <section class="reset__container">
                    <div class="forgot__text">
                        <h2>Forgot your password?</h2>
                        <p>
                            Don’t worry! Just enter your email address and we’ll
                            send you a recovery email.
                        </p>
                    </div>
                    <div class="forgot__form">
                        <input
                            type="email"
                            placeholder="Please provide your email."
                            required
                        />
                    </div>
                    <button class="primary__button forgot__button">Send</button>
                </section>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "ForgotPassword",
    head() {
        return {
            title: "Forgot Password | Haru",
        };
    },
};
</script>

<style>
.forgot__form {
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;
    width: 100%;
    max-width: 50%;
}
.forgot__form > input {
    font-size: 16px;
    text-transform: none;
    font-family: Poppins-Light;
    line-height: 23px;
    color: #383838;
    border: 1px solid hsla(0, 0%, 43.9%, 0.5);
    padding: 9px 14px 8px;
    border-radius: 5px;
    width: 100%;
    margin: 0 auto;
    transition: 0.3s ease-in-out;
}
.forgot__text {
    padding-bottom: 30px;
}
.forgot__text > h2 {
    font-size: 20px;
    text-transform: none;
    font-family: Poppins-Medium;
    color: #383838;
    line-height: 23px;
    margin-bottom: 10px;
    padding: 0 !important;
}
.forgot__button {
    width: 100%;
    max-width: 264px;
    margin-top: 40px;
}
.reset__container {
    width: 100%;
    max-width: 60%;
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #fff;
    border-radius: 10px;
    padding: 48px;
    margin-bottom: 15px;
}
.forgot__password__page {
    height: calc(100vh - 305px);
    margin-top: 6em;
}
.forgot__password__main__container {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
    width: 100%;
    max-width: 80%;
    margin: 0 auto;
}
</style>