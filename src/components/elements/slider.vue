<template>
  <v-container class="slider">
    <div class="swiper__container">
      <div class="swiper-wrapper">
        <div class="swiper-slide">Слайд 1</div>
        <div class="swiper-slide">Слайд 2</div>
        <div class="swiper-slide">Слайд 3</div>
        <!-- Добавьте свои слайды здесь -->
      </div>
      <!-- Кнопки переключения слайдов -->
      <div class="swiper-button-next"></div>
      <div class="swiper-button-prev"></div>
    </div>
  </v-container>
</template>

<script>
import "swiper/swiper-bundle.css"; // импортируйте стили Swiper
import Swiper from "swiper/bundle"; // импортируйте Swiper

export default {
  name: "slider",
  mounted() {
    // Инициализация Swiper после монтирования компонента
    new Swiper(".swiper-container", {
      slidesPerView: 1,
      spaceBetween: 30,
      navigation: {
        nextEl: ".swiper-button-next",
        prevEl: ".swiper-button-prev",
      },
    });
  },
};
</script>

<style lang="scss">
/* Добавьте стили Swiper по необходимости */
.slider {
  max-width: 1520px;
  margin: 0 auto;
  .swiper__container {
    width: 100%;
    height: 100%;
    position: relative;
  }

  .swiper-slide {
    text-align: center;
    padding: 1em;
  }

  .swiper-button-next,
  .swiper-button-prev {
    color: $black;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    z-index: 10;
  }

  .swiper-button-next {
    right: 0;
  }

  .swiper-button-prev {
    left: 0;
  }
}
</style>
