<template>
  <main>
    <section class="slider">
      <swiper ref="mySwiper" :options="swiperOptions">
        <swiper-slide v-for="(slide, index) in slides" :key="index">
          <div class="slider__image">
            <img :src="slide.image" alt="">
          </div>
          <div class="slider__content">
            <div class="slider__title">
              {{ slide.title }}
            </div>
            <div class="slider__description">
              {{ slide.description }}
            </div>
          </div>
        </swiper-slide>
      </swiper>
    </section>

    <section class="deals">
      <h2 class="visually-hidden">
        Deals
      </h2>
      <ul class="deals__items">
        <li class="deals__item">
          <a href="/" class="deals__link deals__link--image-left">
            <h3 class="deals__title">Title</h3>
            <p class="deals__description">
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Minima, pariatur.
            </p>
            <div class="deals__image deals__image--left">.</div>
          </a>
        </li>
        <li class="deals__item">
          <a href="/" class="deals__link deals__link--image-right">
            <h3 class="deals__title">Title</h3>
            <p class="deals__description">
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Minima, pariatur.
            </p>
            <div class="deals__image deals__image--right">.</div>
          </a>
        </li>
      </ul>
    </section>

    <section class="featured">
      <h2 class="visually-hidden">
        Featured categories
      </h2>
      <ul class="featured__items">
        <li class="featured__item">
          <!--фоновое изображение-->
          <h3 class="featured__title">
            Title
          </h3>
        </li>
      </ul>
    </section>

    <section class="customer-banner">
      <h2 class="visually-hidden">
        Contacts
      </h2>
      <p class="customer-banner__text">
        Lorem ipsum dolor sit amet.
      </p>
      <ul class="customer-banner__items">
        <li class="customer-banner__item">
          1
        </li>
        <li class="customer-banner__item">
          2
        </li>
        <li class="customer-banner__item">
          3
        </li>
        <li class="customer-banner__item">
          4
        </li>
      </ul>
    </section>
  </main>
</template>

<script>
import Vue from 'vue';
import {
  Swiper as SwiperClass, Autoplay,
} from 'swiper/swiper.esm';
import getAwesomeSwiper from 'vue-awesome-swiper/dist/exporter';
import 'swiper/swiper.min.css';

SwiperClass.use([Autoplay]);
Vue.use(getAwesomeSwiper(SwiperClass));
const {
  Swiper,
  SwiperSlide,
} = getAwesomeSwiper(SwiperClass);

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      slides: [
        {
          // eslint-disable-next-line global-require
          image: require('../assets/images/slide-1.jpg'),
          description: 'Большая цветовая палитра цветов на любой вкус',
          title: 'Цвета',
        },
        {
          // eslint-disable-next-line global-require
          image: require('../assets/images/slide-2.jpg'),
          description: 'Большой асортимент инстументов',
          title: 'Инстументы',
        },
        {
          // eslint-disable-next-line global-require
          image: require('../assets/images/slide-3.jpg'),
          description: 'Качественные материалы для строительства и ремонта',
          title: 'Материалы',
        },
      ],
      swiperOptions: {
        loop: true,
        autoplay: {
          delay: 5000,
        },
        speed: 400,
      },
    };
  },
  computed: {
    swiper() {
      return this.$refs.mySwiper.$swiper;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "~assets/variables.scss";

.swiper-container {
  height: 100%;
  z-index: 0;
}

.social-links {
  display: flex;
  padding: 0;
  list-style-type: none;

  &__item:not(:first-child) {
    margin-left: 1rem;
  }
}

.featured__items {
  display: flex;
  list-style-type: none;
}

.deals {
  margin-top: 2rem;

  &__items {
    list-style-type: none;
    padding: 0;
  }

  &__item {
    width: 100%;
    height: 150px;
    margin-bottom: 1rem;
    padding: 0 1rem;
  }

  &__link {
    display: flex;
    flex-direction: column;
    position: relative;
    height: 120px;
    margin: 15px 0;
    padding: 1rem 1rem 1rem 1rem;
    background-color: $white;

    &--image-left {
      padding-left: calc(130px + 1rem);
    }

    &--image-right {
      padding-right: calc(130px + 1rem);
    }
  }

  &__title {
    margin-bottom: .5rem;
    font-size: 1.1875rem;
    font-weight: 900;
    line-height: 1.5625rem;
    max-height: 1.5625rem;
    overflow: hidden;
    text-overflow: ellipsis;
    word-break: break-all;
    color: #f36;
  }

  &__description {
    max-height: 2.125rem;
    width: 100%;
    height: 2.4rem;
    overflow: hidden;
    text-overflow: ellipsis;
    color: #333;
    fill: #333;
    font-size: .8125rem;
    line-height: 17px;
  }

  &__image {
    position: absolute;
    top: -1rem;
    width: 150px;
    height: 150px;
    background-image: url(https://jetimages.jetcdn.net/videos/cms_images/web_home/deals_deals2_9Sonos.png);
    background-size: contain;

    &--left {
      left: -0.375rem;
    }

    &--right {
      right: -0.375rem;
    }
  }
}

.slider {
  height: 520px;
  overflow: hidden;
  position: relative;

  &__content {
    position: absolute;
    inset: 0;
    display: flex;
    gap: 1rem;
    align-items: center;
    flex-direction: column;
    justify-content: center;
  }

  &__title {
    font-size: 2.25rem;
    letter-spacing: -2px;
    line-height: 1.111;
    max-height: 3.361em;
    padding-bottom: .11em;
    overflow: hidden;
    text-overflow: ellipsis;
    text-align: center;
    color: $white;
  }

  &__description {
    max-width: 300px;
    padding: .5rem 1rem;
    font-size: 1.25rem;
    background-color: rgba(0, 0, 0, 0.3);
    color: $white;
    border: 3px solid $white;
    text-align: center;
  }

  &__image, img {
    width: 100%;
    height: 100%;
  }

  & img {
    object-fit: cover;
  }
}

.customer-banner {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: .5rem;
  background-color: rgb(54, 0, 96);
  color: $white;

  &__items {
    display: flex;
    padding: 0;
    list-style-type: none;
  }

  &__item:not(:first-child) {
    margin-left: 5px;

    &:before {
      content: ' | ';
    }
  }
}
</style>
