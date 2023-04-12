<template>
    <div class="container">
        <div class="row">
            <div class="col-lg-8">
                <nav aria-label="breadcrumb" class="mt-4">
                    <ol class="breadcrumb">
                        <li class="breadcrumb-item"><nuxt-link to="/">Главная</nuxt-link></li>
                        <li class="breadcrumb-item active" aria-current="page">{{ post.h1 }}</li>
                    </ol>
                </nav>
                <img class="img-fluid rounded mx-auto d-block" :src="post.image" alt="">
                <hr>
                <p v-html="post.content"></p>
                <div class="d-flex justify-content-end">
                    <span v-for="tag in post.tags">
                        <nuxt-link :to="`/tags/${tag}`" class="mr-1 badge text-bg-info me-1">#{{ tag }}</nuxt-link>
                    </span>
                </div>
                <hr>
                <div class="d-flex align-items-center justify-content-end">
                    <div class="mr-auto p-2 lead">Автор: {{ post.author }}</div>
                    <div class="p-2">Опубликовано: {{ post.created_at }}</div>
                </div>
                <hr>
                <Comments />
            </div>
            <Aside />
        </div>
    </div>
</template>

<script>
    import axios from "axios";
    import post_detail from "@/layouts/post_detail";
    import Aside from "@/components/Aside";
    import Comments from "@/components/Comments";
    export default {
        layout: "post_detail",
        components: {
            Aside,
            Comments,
        },
        async asyncData({params}) {
            const post = await axios.get(`http://127.0.0.1:8000/api/posts/${params.slug}`);
            return {
                post: post.data,
            }
        },
    }
</script>

<style scoped></style>