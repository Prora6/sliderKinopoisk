<template>
  <div class="prompts">
    <div class="prompts__carousel-img">
      <VueSlickCarousel ref="carouselImg" :arrows="false">
        <div><img src="../assets/pictures/racer.png" alt="главный герой" class="prompts__character"></div>
        <div><img src="../assets/pictures/racer.png" alt="главный герой" class="prompts__character"></div>
        <div><img src="../assets/pictures/racer.png" alt="главный герой" class="prompts__character"></div>
        <div><img src="../assets/pictures/racer.png" alt="главный герой" class="prompts__character"></div>
      </VueSlickCarousel>
    </div>
    <div class="prompts__cloud"></div>
    <div class="prompts__carousel-text">
      <VueSlickCarousel ref="carouselText" :arrows="false">
        <div><p class="text text_content">Для примера мы показали вам его лицо. В первой серии он прячется в подвале
          за мониторами, и пусть борода не собьёт вас с толку. Найдите героя и нажмите  на паузу —
          ему не терпится отдать вам промокод.</p></div>
        <div><p class="text text_content">Для примера мы показали вам его лицо. В первой серии он прячется в подвале
          за мониторами, и пусть борода не собьёт вас с толку. Найдите героя и нажмите  на паузу —
          ему не терпится отдать вам промокод.</p></div>
        <div><p class="text text_content">Для примера мы показали вам его лицо. В первой серии он прячется в подвале
          за мониторами, и пусть борода не собьёт вас с толку. Найдите героя и нажмите  на паузу —
          ему не терпится отдать вам промокод.</p></div>
        <div><p class="text text_content">Для примера мы показали вам его лицо. В первой серии он прячется в подвале
          за мониторами, и пусть борода не собьёт вас с толку. Найдите героя и нажмите  на паузу —
          ему не терпится отдать вам промокод.</p></div>
      </VueSlickCarousel>
    </div>
      <button class="prompts__prev-slider" v-if="counter !== 1" @click="prev"><ArrowSlide></ArrowSlide></button>
      <button class="prompts__next-slider" v-if="counter !== 8" @click="next"><ArrowSlide></ArrowSlide></button>
    <div class="prompts__interaction">
      <div class="prompts__navigation">
        <div class="menu">
          <MenuBurger/>
        </div>
        <nav class="navigation">
          <div class="navigation__item navigation__item_empty">
          </div>
          <div class="navigation__item navigation__item_empty">
          </div>
          <div class="navigation__item">
            <div class="navigation__title">
              <p class="number">03</p>
              <p class="navigation__text">
                Подсказки
              </p>
            </div>
            <div class="navigation__line"></div>
          </div>
          <div class="navigation__item navigation__item_empty">

          </div>
        </nav>
      </div>
      <div class="prompts__button-scroll">
        <button class="button button_scroll">
          Скрольте вниз
        </button>
        <div class="arrow arrow_scroll">
          <ArrowScroll />
        </div>
      </div>
    </div>
    <div class="prompts__content">
      <div class="prompts__title">
        <div class="logo">
          <LogoSvg/>
        </div>
        <h1 class="title title_content">они должны что-то знать</h1>
        <div class="prompts__counter">{{ counter }}/8</div>
      </div>

      <div class="prompts__description">
        <div class="prompts__button">
          <button class="button button_promo">
            Искать промокод
          </button>
          <div class="arrow arrow_promo">
            <ArrowPromo/>
          </div>
        </div>
      </div>
    </div>
    <div class="prompts__right-group">
      <a class="link prompts__link" href="#">hd.kinopoisk.ru</a>
    </div>

  </div>
</template>

<script>
import LogoSvg from "@/components/LogoSvg";
import ArrowPromo from "@/components/ArrowPromo";
import MenuBurger from "@/components/MenuBurger";
import ArrowScroll from "@/components/ArrowScroll";
import ArrowSlide from "./ArrowSlide";
import VueSlickCarousel from 'vue-slick-carousel'
import 'vue-slick-carousel/dist/vue-slick-carousel.css'
export default {
  name: 'HelloWorld',
  props: {
  },
  components: {
    LogoSvg,
    ArrowPromo,
    MenuBurger,
    ArrowScroll,
    ArrowSlide,
    VueSlickCarousel
  },
  data() {
    return {
      counter: 1
    }
  },
  methods: {
    prev() {
      this.$refs.carouselImg.prev();
      this.$refs.carouselText.prev();
      if (this.counter !== 1) {
        this.counter -=1;
      }
    },
    next() {
      this.$refs.carouselImg.next();
      this.$refs.carouselText.next();
      if (this.counter !== 8) {
        this.counter +=1;
      }
    },


  }
}
</script>

<style lang="scss">
.newSlide{
  max-width: 902px;
  width: 100%;
  position: absolute;
  top: 67%;
  left: 48%;
  transform: translate(-50%, -50%);
  &__slide {
    display: flex;
  }
}

* {
  box-sizing: border-box;
}
body {
  margin: 0;
}
p, h1, h2, h3 {
  margin: 0;
}

ul {
  margin: 0;
  padding: 0;
  list-style-type: none;
}
</style>