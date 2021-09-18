<template>
  <BaseSection className="invite">

    <div class="invite__wrapper">
      <div class="invite__content">
        <h3>Приглашение в демо-зал «Катюша»</h3>
        <form class="invite__form">
          <div class="invite__fields">
            <BaseField placeholder="Ваше имя" required/>
            <BaseField placeholder="Название компании" required/>
          </div>
          <BaseButton>Оставить заявку!</BaseButton>
        </form>
      </div>
      <div class="invite__slider">
        <div v-swiper="this.swiperOptions" @ready="test">
          <div class="swiper-wrapper">
            <!-- <div class="swiper-slide" :key="banner" v-for="banner in banners"> -->
            <div class="swiper-slide">
              <img class="temp__img" src="~/../src/images/slide01.jpg" alt=""/>
            </div>
            <div class="swiper-slide">
              <div>asss</div>
            </div>
            <div class="swiper-slide">
              <div>asdddd</div>
            </div>
          </div>
        </div>
        <Icon icon="arrow_left" class="temp__arrow_prev" @click.native="prev()"/>
        <Icon icon="arrow_right" class="temp__arrow_next" @click.native="next()"/>
      </div>

    </div>

    <!-- <div class="invite__images">s
      <div>asd</div>
      <div>asss</div>
      <div>asdddd</div>
    </div> -->

  </BaseSection>
</template>

<script>
import { directive } from 'vue-awesome-swiper';
import 'swiper/css/swiper.css';
export default {
  name: 'SectionInvite',
  props: {},
  data() {
    swiper: null;
    return {
      swiperOptions: {
        slidesPerView: 1,
        //allowTouchMove: false,
        // navigation: {
        //   nextEl: '.temp__arrow_next',
        //   prevEl: '.temp__arrow_prev',
        // },
      }
    }
  },
  directives: {
    swiper: directive,
  },
  mounted() {
    console.log(this.$refs)
  },
  methods: {
    test(q) {
      console.log(q)
      this.swiper = q;
      //q.init(opts);
    },
    next() {
      this.swiper.slideNext()
    },
    prev() {
      this.swiper.slidePrev()
    }
  },
}
</script>

<style lang="scss">
.invite {

  &__wrapper {
    //display: grid;
    //grid-template-columns: minmax(auto, 620px) minmax(auto, 780px);

    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    gap: 30px;
  }

  &__slider {
    max-width: 780px;
    width: 100%;
    position: relative;

    border-radius: 10px;
    overflow: hidden;
    &:after {
      content: '';
      position: absolute;
      width: 100%;
      height: 100%;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background: linear-gradient(90deg, rgba(0, 0, 0, 0.4) 0%, rgba(0, 0, 0, 0) 50%, rgba(0, 0, 0, 0.4) 100%);
      z-index: 1
    }
  }

  .temp {
    &__wrapper {
      position: relative;
      width: 100%;
      height: 100%;
      z-index: 1;
      display: flex;
      transition-property: transform;
      box-sizing: content-box;
      transform: translate3d(0px, 0, 0);
    }
    &__img {
      width: 100%;
      height: 100%;
      display: block;
    }
    &__item {
      flex-shrink: 0;
      width: 100%;
      height: 100%;
      position: relative;
      transition-property: transform;
    }

    &__arrow {
      &_prev, &_next {
        cursor: pointer;
        color: get-variable(color, white);
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        width: 14px;
        height: 24px;
        z-index: 2;
      }
      &_prev {
        left: 20px;
      }
      &_next {
        right: 20px;
      }
    }
  }

  &__content {
    max-width: 620px;
    width: 100%;
  }
  &__form {
    @include flex-container(column, 40px);
  }
  &__fields {
    @include flex-container(column, 30px);
  }
}
</style>
