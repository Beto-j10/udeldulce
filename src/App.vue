<script setup>

import IconColors from './components/icons/iconColors.vue';
import Carousel from './components/Carousel.vue';
import IconInstagram from './components/icons/iconInstagram.vue';
import IconWhatsapp from './components/icons/iconWhatsapp.vue';
import IconEmail from './components/icons/iconEmail.vue';
import { onMounted } from 'vue';

onMounted(() => {
    const intro = document.getElementById('intro');
    intro.onanimationend = () => {
        intro.classList.add('hidden');
    }
})

</script>

<template>
    <div class="container">
        <header class="header">
            <IconColors :width="192" position="top" />
            <IconColors :width="192" position="bottom" />
            <img class="header__image" src="./assets/images/splash.png" />
            <h1 class="header__text">
                Universidad
                <span class="header__text header__text--small">• Del Dulce •</span>
            </h1>
        </header>

        <main class="main">
            <div class="list__container">
                <span class="list__title">Distribuidores</span>
                <ul class="list">
                    <li>Dulces</li>
                    <li>Chocolates</li>
                    <li>Galletas</li>
                </ul>
            </div>
            <Carousel />
            <div class="contact">
                <div class="contact__whatsapp">
                    <IconWhatsapp :size="40" />
                    <span class="contact__whatsapp--text">Escríbenos</span>
                    <a
                        href=" https://api.whatsapp.com/send?phone=573133260448&text=%C2%A1Hola!%20me%20gustar%C3%ADa%20saber%20m%C3%A1s."
                        target="_blank"
                    ></a>
                </div>

                <div class="contact__instagram">
                    <IconInstagram :size="72" />
                    <a href="https://www.instagram.com/universidaddeldulce/" target="_blank"></a>
                </div>
                <div class="contact__email">
                    <IconEmail :size="24" />
                    <span>hola@udeldulce.com</span>
                </div>
            </div>
        </main>

        <footer class="footer">© 2022 udeldulce.com • All rights reserved</footer>
        <div id="intro" class="loader">
            <img class="animation__candy" src="./assets/images/candy2.png" alt />
        </div>
    </div>
</template>

<style>
@import "./assets/base.css";
@import url("https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;500;600;700&display=swap");

.container {
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: min-content minmax(min-content, 1fr) min-content;
    grid-template-areas:
        "header"
        "main"
        "footer";
    height: 100%;
}

.header {
    grid-area: header;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    padding-top: 24px;
}

.header__text {
    font-size: 2.6rem;
    font-weight: bold;
    color: #fff;
}

.header__text--small {
    display: block;
    text-align: center;
    font-size: var(--font-size-x-large);
    top: -8px;
}

.header__image {
    width: 320px;
    position: fixed;
    right: -160px;
    top: -192px;
    pointer-events: none;
}

.main {
    grid-area: main;
    overflow-x: hidden;
    display: flex;
    flex-flow: row wrap;
    align-items: flex-end;
    justify-content: center;
    height: 100%;
}

.list__container {
    position: relative;
    font-family: "Dancing Script", cursive;
    font-size: 2.4rem;
    color: #fff;
    text-align: center;
    line-height: 1.2;
    /* align-self: center; */
}

.list__title {
    font-family: Montserrat;
    font-size: var(--font-size-large);
    /* font-style: italic; */
    font-weight: 700;
    margin: 10px 0 8px;
    display: block;
}

.list__image {
    width: 200px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    pointer-events: none;
    filter: opacity(30%);
}

.list {
    list-style: none;
    padding: 0;
}

.contact {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
}

.contact__whatsapp {
    background-color: var(--color-background-soft);
    /* background-color: #ff7600; */
    align-self: flex-end;
    padding: 6px 10px;
    border-radius: 12px 0 0 12px;
    display: flex;
    flex-direction: column;
    align-items: center;
    color: #fff;
}

.contact__whatsapp--text {
    display: none;
}

.contact__instagram {
    line-height: 0;
}

.contact__email {
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: var(--font-size-large);
    color: #fff;
    font-weight: 500;
    gap: 0.5em;
    margin: 8px 0 16px;
}

.footer {
    grid-area: footer;
    display: flex;
    justify-content: center;
    align-items: center;
    font-weight: 500;
    font-size: var(--font-size-x-small);
    color: var(--color-text-secondary);
    padding: 0.5rem 0;
}

.loader {
    position: fixed;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
    z-index: 3;
    background-color: transparent;
}

.animation__candy {
    animation: scale_candy 0.8s ease-in 1 normal;
}

.hidden {
    display: none;
}

@keyframes scale_candy {
    0% {
        transform: scale(1) rotate(-0.2turn);
    }
    40% {
        transform: scale(2);
    }
    100% {
        transform: scale(0) rotate(1.2turn);
    }
}

#app {
    /* max-width: 1280px; */
    margin: 0 auto;
    font-weight: normal;
    height: 100%;
}

header {
    line-height: 1.5;
}
a {
    cursor: pointer;
    line-height: 0;
    text-decoration: none;
    color: inherit;
    position: absolute;
    height: 100%;
    width: 100%;
    top: 0;
    left: 0;
}
/* @media (hover: hover) {
    a:hover {
        cursor: pointer;
    }
} */

@media (min-width: 1024px) {
    .header {
        padding-top: 8px;
    }
    .header__text {
        font-size: 3.2rem;
    }
    .header__text--small {
        font-size: 2.2rem;
    }
    .header__image {
        width: 384px;
        right: -184px;
        top: -216px;
    }
    .list__container {
        font-size: 2.6rem;
    }

    .contact__whatsapp {
        transition: padding-right 0.2s ease-in-out;
    }

    .contact__whatsapp:hover {
        padding-right: 30px;
        transition: padding-right 0.2s ease-in-out;
    }

    .contact__whatsapp--text {
        display: flex;
    }

    .contact__instagram {
        transition: transform 0.2s ease-in-out;
    }

    .contact__instagram:hover {
        transform: scale(1.05);
        transition: transform 0.2s ease-in-out;
    }
}

/* @media (min-width: 1280px) {
    .contact__whatsapp {
        border-radius: 12px;
    }
    .contact__whatsapp:hover {
        padding: 6px 10px;
        transform: scale(1.2);
        transition: transform 0.2s ease-in-out;
    }
} */
</style>
