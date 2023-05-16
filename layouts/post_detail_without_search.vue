<template>
    <div>
        <Navbar />
        <Nuxt />
        <Footer />
    </div>
</template>


<script>
    import Navbar from "~/components/NavbarWithoutSearch";
    import Footer from "~/components/Footer";

    export default {
        components: {
            Footer,
            Navbar,
        }
    };
</script>

<style></style>