<template>
    <div class="main">
        <div class="story__banner">
            <h2>Our Story</h2>
        </div>
        <div class="url story__url">
            <NuxtLink to="/"> HOME </NuxtLink> /
            <NuxtLink to="/our-story"> OUR STORY </NuxtLink>
        </div>

        <div class="story__description">
            <p>
                Lorem, ipsum dolor sit amet consectetur adipisicing elit.
                Doloribus at minima deserunt porro magni cumque accusantium
                dolores qui! Dolore vitae labore, quidem facere alias assumenda
                voluptate non vel accusamus eligendi.
            </p>
        </div>

        <div class="story__container">
            <div class="story__inline">image</div>
            <div class="story__inline">
                <h2>Our Mission &amp; Vision</h2>
                <p>
                    Lorem ipsum dolor, sit amet consectetur adipisicing elit.
                    Necessitatibus porro excepturi omnis ipsum architecto
                    molestiae sapiente officia dignissimos officiis odit, nobis,
                    laborum deleniti culpa sint laudantium aspernatur aut dolor
                    iste.
                </p>
            </div>
        </div>

        <div class="story__container">
            <div class="story__inline">
                <h2>Our Products and Services</h2>
                <p>
                    Lorem ipsum dolor, sit amet consectetur adipisicing elit.
                    Necessitatibus porro excepturi omnis ipsum architecto
                    molestiae sapiente officia dignissimos officiis odit, nobis,
                    laborum deleniti culpa sint laudantium aspernatur aut dolor
                    iste.
                </p>
            </div>
            <div class="story__inline">image</div>
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
/* .main > div {
    align-items: center;
} */
.story__banner {
    text-align: center;
}
.story__container, .story__description, .story__url {
    padding-left: 15em;
    padding-right: 15em;
}
.story__inline {
    width: 50%;
    /* float: left; */
}
</style>