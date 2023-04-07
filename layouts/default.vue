<template>
    <div>
        <Navbar />
        <Carousel />
        <Nuxt />
        <Footer />
    </div>
</template>


<script>
    import Navbar from "~/components/Navbar";
    import Carousel from "~/components/Carousel";
    import Footer from "~/components/Footer";

    export default {
        components: {
            Navbar,
            Footer,
            Carousel,
        }
    };
</script>

<style>
</style>