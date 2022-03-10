<template>
    <div class="main">
        <!-- Banner -->
        <section class="story__banner">
            <img src="/images/pages/our_story.jpg" />
            <div class="story__overlay">
                <div class="container">
                    <div class="story__title">Our Story</div>
                </div>
            </div>
        </section>
        <div class="main_container story__main__container">
            <div id="breadcrumb">
                <ul>
                    <li>
                        <NuxtLink to="/" class="breadcrumb__link">
                            HOME
                        </NuxtLink>
                        <span class="slash"> / </span>
                    </li>
                    <li>
                        <NuxtLink to="/our-story" class="breadcrumb__link">
                            <span class="breadcrumb__link__active"
                                >OUR STORY</span
                            >
                        </NuxtLink>
                    </li>
                </ul>
            </div>

            <div class="story__description">
                <p>
                    Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed
                    diam nonumy eirmod tempor invidunt ut labore et dolore magna
                    aliquyam erat, sed diam voluptua. At vero eos et accusam et
                    justo duo dolores et ea rebum. Stet clita kasd gubergren, no
                    sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem
                    ipsum dolor sit amet, consetetur sadipscing elitr, sed diam
                    nonumy eirmod.
                </p>
            </div>
            <section>
                <div class="story__left">
                    <img src="/images/pages/our_mission_vision.png" alt="" />
                </div>
                <div class="story__right">
                    <h2>Our Mission &amp; Vision</h2>
                    <p>
                        Lorem ipsum dolor, sit amet consectetur adipisicing
                        elit. Necessitatibus porro excepturi omnis ipsum
                        architecto molestiae sapiente officia dignissimos
                        officiis odit, nobis, laborum deleniti culpa sint
                        laudantium aspernatur aut dolor iste.
                    </p>
                </div>
            </section>
            <section class="reverse">
                <div class="story__left">
                    <img src="/images/pages/our_products_services.png" alt="" />
                </div>
                <div class="story__right">
                    <h2>Our Products and Services</h2>
                    <p>
                        Lorem ipsum dolor, sit amet consectetur adipisicing
                        elit. Necessitatibus porro excepturi omnis ipsum
                        architecto molestiae sapiente officia dignissimos
                        officiis odit, nobis, laborum deleniti culpa sint
                        laudantium aspernatur aut dolor iste.
                    </p>
                </div>
            </section>
        </div>
    </div>
</template>

<script>
export default {
    name: "OurStory",
    head() {
        return {
            title: "Our Story | Haru",
        };
    },
};
</script>

<style>
.story__overlay {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    align-items: center;
    justify-content: center;
}
.story__title {
    font-size: 38px;
    text-transform: none;
    font-family: CrimsonText-SemiBold;
    color: #fff;
    text-align: center;
}
.story__container {
    padding: 0 60px;
}
.story__banner {
    position: relative;
    margin-top: 5em;
}
.story__description {
    padding: 60px 0 102px;
}
.story__main__container {
    margin-top: 0;
}
.story__main__container > section {
    display: flex;
}
.story__main__container > section > div > h2 {
    font-size: 24px;
    text-transform: none;
    font-family: Poppins-Medium;
    color: #383838;
    line-height: 40px;
    margin-bottom: 0;
}
.reverse {
    flex-direction: row-reverse;
}
.story__main__container > section > div > p {
    font-size: 16px;
    text-transform: none;
    font-family: Poppins-Light;
    color: #383838;
    line-height: 24px;
}
.story__left {
    flex: 0 0 50%;
    margin-bottom: 90px;
}
.story__right {
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-flow: column wrap;
    padding-left: 50px;
    margin-bottom: 90px;
}
.story__banner > img {
    width: 100%;
}
.story__container,
.story__url {
    padding-left: 15em;
    padding-right: 15em;
}
.story__inline {
    width: 50%;
    /* float: left; */
}
</style>