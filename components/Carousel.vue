<template>
    <div id="carousel" class="container carousel slide my-0" data-bs-ride="carousel" data-bs-interval="1500">
        <div class="carousel-indicators">
            <button type="button" data-bs-target="#carousel" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
            <button type="button" data-bs-target="#carousel" data-bs-slide-to="1" aria-label="Slide 2"></button>
            <button type="button" data-bs-target="#carousel" data-bs-slide-to="2" aria-label="Slide 3"></button>
        </div>
        <div class="carousel-inner">
            <div class="carousel-item active">
            <img src="http://placeimg.com/800/300/any" class="d-block w-100" alt="...">
            <div class="carousel-caption d-none d-md-block">
                <h5>Назване 1-ого слайда</h5>
                <p>Некоторый текст для 1-ого слайда.</p>
            </div>
            </div>
            <div class="carousel-item">
            <img src="http://placeimg.com/800/300/dump" class="d-block w-100" alt="...">
            <div class="carousel-caption d-none d-md-block">
                <h5>Назване 2-ого слайда</h5>
                <p>Некоторый текст для 2-ого слайда.</p>
            </div>
            </div>
            <div class="carousel-item">
            <img src="http://placeimg.com/800/300/age" class="d-block w-100" alt="...">
            <div class="carousel-caption d-none d-md-block">
                <h5>Назване 3-го слайда</h5>
                <p>Некоторый текст для 3-го слайда.</p>
            </div>
            </div>
        </div>
        <button class="carousel-control-prev" type="button" data-bs-target="#carousel" data-bs-slide="prev">
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Предыдущий</span>
        </button>
        <button class="carousel-control-next" type="button" data-bs-target="#carousel" data-bs-slide="next">
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Следующий</span>
        </button>
    </div>
</template>

<script>
    export default {
        name: 'Carousel'
    }
</script>

<style scoped>

</style>