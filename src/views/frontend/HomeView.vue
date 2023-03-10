<template>

  <!-- 暢銷餐點 start -->
  <div class="hot-food-bg bg-size-contain bg-no-repeat py-8 py-lg-20">
    <div class="text-center">
      <h2 class="block-title position-relative fs-3 fs-lg-2 fw-lg-bold mb-5 mb-lg-10">暢銷餐點</h2>
    </div>
    <div class="container position-relative mb-5 mb-lg-10">
      <SwiperHotFood></SwiperHotFood>
    </div>
    <div class="text-center">
      <a href="#/products" class="btn btn-primary fs-lg-5 px-5 py-3 px-lg-6">更多餐點</a>
    </div>
  </div>
  <!-- 暢銷餐點 end -->
  <!-- 好評推薦 start -->
  <div class="bg-primary-light py-8 py-lg-20">
    <div class="text-center">
      <h2 class="block-title position-relative fs-3 fs-lg-2 fw-lg-bold mb-5 mb-lg-10" style="z-index: 0">好評推薦</h2>
    </div>
    <div class="container">
      <SwiperComment></SwiperComment>
    </div>
  </div>
  <!-- 好評推薦 end -->

</template>
<style lang="scss">
  // banner start
  .home-banner {
    height: 598px;
    background-image: url(@/assets/image/banner-home-sm.png);
    @include mobile() {
      height: 642px;
      background-image: url(@/assets/image/banner-home-lg.png);
    }
  }
  .home-banner-logo {
    @include mobile() {
      width: 200px;
      height: 200px;
    }
  }
  // banner end
  // 每個區塊 title 偽元素 start
  .block-title {
    display: inline-block;
    &::after {
      content: '';
      position: absolute;
      width: 84px;
      height: 64px;
      background-size: contain;
      background-image: url(@/assets/image/title.svg);
      top: -17px;
      right: -20px;
      z-index: -1;
      @include mobile() {
        width: 102px;
        height: 77px;
        top: -24px;
        right: -29px;
      }
    }
  }
  // 每個區塊 title 偽元素 end
  // 七大堅持 start
  .feature-bg {
    @include mobile() {
      background-position: -50px -50px, 102% 109%;
      background-size: 691px 451px, 617px 520px;
      background-image: url(@/assets/image/feature-bg01.svg), url(@/assets/image/feature-bg02.svg);
    }
  }
  .feature-icon {
    @include mobile() {
      width: 64px;
      height: 64px;
    }
  }
  .feature-number {
    font-size: 155px;
    z-index: -10;
    top: -12px;
    left: 0px;
    @include mobile() {
      top: -5px;
      left: -20px;
    }
  }
  // 七大堅持 end
  // 暢銷餐點 start
  .hot-food-bg {
    background-image: url(@/assets/image/hot-food-bg-sm.svg);
    background-position: bottom right;
    @include mobile() {
      background-image: url(@/assets/image/hot-food-bg.svg);
    }
  }
  // 暢銷餐點 end
  // 常見問題 start
  .accordion-button {
    padding: 20px 24px;
    border: 2px solid transparent;
  }
  .accordion-button.collapsed {
    border: 2px solid transparent;
  }
  .accordion-button:not(.collapsed) {
    background-color: #fafafa;
    box-shadow: none;
    border: 2px solid #dfebe3;
  }

  .accordion-flush .accordion-item .accordion-button,
  .accordion-flush .accordion-item .accordion-button.collapsed {
    border-radius: 8px;
  }
  .accordion-button {
    background-color: #fafafa;
  }
  // 取消按鈕 focus 樣式
  .accordion-button:focus {
    box-shadow: none;
  }
  // icon
  .accordion-button:not(.collapsed)::after {
    width: 32px;
    height: 32px;
    background-size: contain;
  }
  .accordion-button::after {
    width: 32px;
    height: 32px;
    background-size: contain;
  }
  .accordion-item {
    border: 0px solid transparent;
  }

  // 常見問題 end
</style>
<script>
  // import { RouterLink } from 'vue-router';
  // import { Swiper, SwiperSlide } from 'swiper/vue';
  // import { Autoplay, Navigation, Pagination } from 'swiper';
  import SwiperComment from '@/components/frontend/SwiperComment.vue';
  import SwiperHotFood from '@/components/frontend/SwiperHotFood.vue';

  // Import Swiper styles
  // import 'swiper/css';
  // import 'swiper/css/navigation';
  // import 'swiper/css/pagination';

  // const { VITE_URL, VITE_PATH } = import.meta.env;

  export default {
    // data() {
    //   return {
    //     modules: [Navigation, Pagination, Autoplay],
    //     navigation: {
    //       nextEl: '.swiper-button-next',
    //       prevEl: '.swiper-button-prev',
    //     },
    //     swiperOptions: {
    //       breakpoints: {
    //         1200: {
    //           slidesPerView: 4,
    //           spaceBetween: 40,
    //         },
    //         576: {
    //           slidesPerView: 3,
    //           spaceBetween: 30,
    //         },
    //         376: {
    //           slidesPerView: 2,
    //           spaceBetween: 20,
    //         },
    //         0: {
    //           slidesPerView: 1.58,
    //           spaceBetween: 16,
    //         },
    //       },
    //     },
    //     products: [],
    //     tempProduct: {},
    //   };
    // },
    components: {
      // Swiper,
      // SwiperSlide,
      // RouterLink,
      SwiperComment,
      SwiperHotFood,
    },
    // methods: {
    //   getProducts() {
    //     this.$http
    //       .get(`${VITE_URL}/api/${VITE_PATH}/products/all`)
    //       .then((res) => {
    //         this.products = res.data.products;
    //       })
    //       .catch((err) => {
    //         alert(err.response.data.message);
    //       });
    //   },
    //   getProduct(id) {
    //     this.$http
    //       .get(`${VITE_URL}/api/${VITE_PATH}/product/${id}`)
    //       .then((res) => {
    //         this.tempProduct = res.data.product;
    //       })
    //       .catch((err) => {
    //         alert(err.response.data.message);
    //       });
    //   },
    // },
    // mounted() {
    //   this.getProducts();
    // },
  };
</script>
