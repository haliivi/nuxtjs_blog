<template>
    <div>
        <div class="container-fluid home-slider">
            <form class="d-flex my-2 my-lg-0">
                <input name="q" type="text" class="form-control me-2" placeholder="Поиск" aria-label="Поиск" v-model="q">
                <button class="btn btn-outline-success" @click.stop.prevent="searchPosts()">Поиск</button>
            </form>
        </div>
    </div>
</template>

<script>
    import axios from "axios";
    export default {
        data() {
            return {
                q: '',
                posts: ''
            }
        },
        methods: {
            async searchPosts() {
                this.posts = await axios.get(`http://127.0.0.1:8000/api/posts/?q=${this.q}`);
                this.$router.push("/search?q="+this.q);
                this.$emit('searchPosts', this.posts.data);
            },
        }
    }
</script>

<style scoped>

</style>