<script setup>
const imagesDir = []
for (let i = 1; i <= 21; i++) {
    imagesDir.push(`/products/image_${i}.png`);

}
</script>

<template>
    <div class="carousel__container">
        <div class="carousel">
            <div class="carousel__card" v-for="src of imagesDir">
                <img class="carousel__image" :src="src" />
            </div>
        </div>
    </div>
</template>

<style scoped>
.carousel__container {
    position: relative;
    display: flex;
    overflow: hidden;
    height: min-content;
    width: 100%;
    pointer-events: none;
}

.carousel__container::after {
    position: absolute;
    content: "";
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(
        90deg,
        rgba(82, 0, 106, 1) 0%,
        rgba(82, 0, 106, 0) 35%,
        rgba(82, 0, 106, 0) 65%,
        rgba(82, 0, 106, 1) 100%
    );
}

.carousel {
    display: flex;
    align-items: center;
    animation: movement 50s linear 0s infinite normal;
    padding-left: 100%;
}

.carousel__card {
    padding: 0 64px 0 0;
}

.carousel__image {
    width: 144px;
    object-fit: contain;
}

@keyframes movement {
    from {
        transform: translateX(0);
    }
    to {
        transform: translateX(-100%);
    }
}

@media (min-width: 1024px) {
    .carousel {
        animation: movement 70s linear 0s infinite normal;
    }
    .carousel__card {
        padding: 0 92px 0 0;
    }
    .carousel__image {
        width: 192px;
    }
}
</style>