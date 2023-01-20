<template>
  <section class="testimonials-section pb-90">
    <div class="container">
      <div class="row">
        <div class="section-title">
          <h2>SERVICES WE PROVIDE</h2>
        </div>
      </div>
      <div class="row">
        <div class="col-md-12 testimonials-carousel-4">
          <swiper
            :options="swiperOption"
            class="owl-carousel"
            v-if="services.length >= 1"
          >
            <swiper-slide v-for="service in services" :key="service.id">
              <div class="item">
                <div class="testimonials-col">
                  <div class="thumb">
                    <img :src="service.image" :alt="service.title" />
                  </div>
                  <div class="content">
                    <h4>{{ service.title }}</h4>
                    <h6>{{ service.description.substring(0, 200) + "..." }}</h6>
                  </div>
                </div>
              </div>
            </swiper-slide>

            <div class="swiper-button-next" slot="button-next"></div>
            <div class="swiper-button-prev" slot="button-prev"></div>
          </swiper>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AppHomeServices",
  props: ["services"],
  data() {
    return {
      swiperOption: {
        loop: true,
        slidesPerView: 1,
        spaceBetween: 20,
        navigation: {
          nextEl: ".swiper-button-prev",
          prevEl: ".swiper-button-next",
        },
        breakpoints: {
          // when window width is >= 320px
          100: {
            slidesPerView: 1,
          },
          // when window width is >= 480px
          480: {
            slidesPerView: 1,
          },
          // when window width is >= 640px
          640: {
            slidesPerView: 2,
          },
          992: {
            slidesPerView: 3,
          },
          1200: {
            slidesPerView: 4,
          },
        },
      },
    };
  },
  methods: {},
};
</script>
<style>
.testimonials-carousel-4 {
  position: relative;
}
.testimonials-carousel-4 .owl-carousel {
  background: #fff;
}
.testimonials-carousel-4 .owl-carousel .owl-item {
  padding: 35px 15px;
}
.testimonials-carousel-4 .owl-theme .owl-nav .owl-next,
.testimonials-carousel-4 .owl-theme .owl-nav .owl-next:hover,
.testimonials-carousel-4 .owl-theme .owl-nav .owl-prev,
.testimonials-carousel-4 .owl-theme .owl-nav .owl-prev:hover {
  background-color: var(--main-color);
  color: transparent;
  display: inline-block;
  height: 75px;
  width: 24px;
  top: 197px;
  text-align: center;
  line-height: 75px;
  font-size: 18px;
  position: absolute;
}

.thumb {
  width: 100%;
}

.testimonials-carousel-4 .owl-carousel .item img {
  height: 120px;
  width: 100%;
  border-radius: 0;
  object-fit: contain;
}
.testimonials-carousel-4 .owl-nav .owl-next {
  right: 0px;
}
.testimonials-carousel-4 .owl-nav .owl-prev {
  left: 0px;
}
.next {
  display: inline-block;
  top: 232px;
  text-align: center;
  line-height: 75px;
  font-size: 18px;
  position: absolute;
  color: #fff;
  right: 24px;
  z-index: 2;
}
.prev {
  display: inline-block;
  top: 232px;
  text-align: center;
  line-height: 75px;
  font-size: 18px;
  position: absolute;
  color: #fff;
  left: 24px;
  z-index: 2;
}
</style>
