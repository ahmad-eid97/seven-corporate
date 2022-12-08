<template>
  <section class="testimonial-section pb-70">
    <div class="container">
      <div class="row testimonials-post">
        <div class="col-md-12">
          <swiper
            :options="swiperOption"
            class="owl-carousel"
            v-if="testimonials.length >= 1"
          >
            <swiper-slide v-for="item in testimonials" :key="item.id">
              <div class="item">
                <div class="testimonials-item">
                  <div class="thumb">
                    <img :src="item.image" :alt="item.name" />
                  </div>
                  <div class="content">
                    <h3>{{ item.name }} - {{ item.job }}</h3>
                    <p>{{ item.description }}</p>
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
  name: "AppHomeTestimonials",
  props: ["testimonials"],
  data() {
    return {
      swiperOption: {
        loop: true,
        slidesPerView: 1,
        spaceBetween: 50,
        navigation: {
          nextEl: ".swiper-button-prev",
          prevEl: ".swiper-button-next",
        },
      },
    };
  },
  methods: {},
};
</script>
<style>
.testimonials-post::after {
  content: none !important;
}
.testimonials-post {
  padding: 0px !important;
  position: relative;
}
.testimonials-post .owl-carousel {
  background-color: transparent;
}
.testimonials-post .testimonials-item {
  padding: 0px 70px;
}
.testimonials-post .owl-carousel .owl-item {
  padding: 35px 15px;
}
.testimonials-post .owl-theme .owl-nav .owl-next,
.testimonials-post .owl-theme .owl-nav .owl-next:hover,
.testimonials-post .owl-theme .owl-nav .owl-prev,
.testimonials-post .owl-theme .owl-nav .owl-prev:hover {
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
.testimonials-post .owl-nav .owl-next {
  right: 0px;
}
.testimonials-post .owl-nav .owl-prev {
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
