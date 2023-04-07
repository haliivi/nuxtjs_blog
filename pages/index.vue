<template>
    <div class="container">
        <h1 class="my-3 text-center">Последние записи блога</h1>
        <div class="row">
            <div v-for="post in posts" :key="post.slug" class="col-md-4">
                <div class="card mb-4">
                    <img :src="post.image" class="card-img-top" alt="...">
                    <div class="card-body">
                        <h5 class="card-title">{{ post.h1 }}</h5>
                        <div v-html="post.description" class="truncate"></div>
                        <nuxt-link v-for="tag in post.tags" :to="`/tags/${tag}`" class="badge text-bg-info me-1">
                            #{{ tag }}
                        </nuxt-link>
                        <div class="d-flex justify-content-between align-items-center mt-4">
                            <nuxt-link :to="`/posts/${post.slug}`" class="btn btn-primary">Перейти</nuxt-link>
                            <small class="text-muted">{{ post.created_at }}</small>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import axios from 'axios';
    export default {

        async asyncData(ctx) {
            const { data } = await axios.get(`http://127.0.0.1:8000/api/posts/`);
            return {
                posts: data.results,
            }
        }
    }
</script>

<style>

</style>