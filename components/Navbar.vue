<template>
    <nav class="navbar navbar-expand-lg bg-dark fixed-top" data-bs-theme="dark">
        <div class="container-fluid">
            <nuxt-link to="/" class="navbar-brand">
                <img src="https://upload.wikimedia.org/wikipedia/commons/c/c3/Python-logo-notext.svg" width="30" height="30" alt="logo">
            </nuxt-link>
            <nuxt-link to="/" class="navbar-brand">
                <img src="https://upload.wikimedia.org/wikipedia/commons/a/ae/Nuxt_logo.svg" width="30" height="30" alt="logo">
            </nuxt-link>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                    <li class="nav-item">
                        <nuxt-link class="nav-link active" aria-current="page" to="/">Главная</nuxt-link>
                    </li>
                    <li class="nav-item">
                        <nuxt-link class="nav-link" to="/contact">Контакты</nuxt-link>
                    </li>
                </ul>
                <ul class="navbar-nav">
                    <form class="d-flex" role="search">
                        <input name="q" v-model="q" class="form-control me-2" type="search" placeholder="Поиск..." aria-label="Search">
                        <button class="btn btn-outline-success" type="submit" @click.stop.prevent="submit()">Поиск</button>
                    </form>
                    <li class="nav-item">
                        <nuxt-link class="nav-link" to="/signup">Регистрация</nuxt-link>
                    </li>
                    <span class="navbar-text">Username</span>
                    <li class="nav-item">
                        <nuxt-link class="nav-link" to="/signin">Вход</nuxt-link>
                    </li>
                    <li class="nav-item">
                        <nuxt-link class="nav-link" to="/signout">Выход</nuxt-link>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<script>
    export default {
        name: "Navbar",
        data() {
            return {
                q : null
            }
        },
        methods: {
            submit() {
                this.$router.push('/search?q='+this.q);
            }
        }
    }
</script>
<style scoped></style>