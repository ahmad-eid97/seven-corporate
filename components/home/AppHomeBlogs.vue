<template>
  <section class="blog-section bg-f8">
    <div class="container">
      <div class="row">
        <div class="section-title">
          <h2>WELCOME TO SEVEN CORPORATE!</h2>
        </div>
      </div>
      <div class="row">
        <div class="col-md-6 col-lg-4 slider-container">
          <swiper :options="swiperOption" class="owl-carousel">
            <swiper-slide v-for="item in testimonials" :key="item.id">
              <div class="item">
                <div class="projects-col">
                  <div class="thumb">
                    <img :src="item.image" :alt="item.title" />
                  </div>
                  <div class="content">
                    <h4>{{ item.title }}</h4>
                    <h5>{{ item.job }}</h5>
                    <h6>{{ item.description }}</h6>
                  </div>
                </div>
              </div>
            </swiper-slide>
            <div class="swiper-button-next" slot="button-next"></div>
            <div class="swiper-button-prev" slot="button-prev"></div>
          </swiper>
        </div>
        <div class="col-md-6 col-lg-4">
          <div class="">
            <div
              v-for="item in features.find(
                (one) => one.key === 'features_text_list'
              ).value"
              :key="item"
              class="overview-item mb-20"
            >
              <div class="overview-icon">
                <h4 class="one"><i :class="item.icon"></i></h4>
              </div>
              <div class="overview-details">
                <h3 class="title">{{ item.title }}</h3>
                <p class="text-black">{{ item.description }}</p>
              </div>
            </div>
          </div>
        </div>
        <div class="col-md-6 col-lg-4">
          <div class="">
            <div class="thumb">
              <img alt="" :src="blogs[0].image" />
            </div>

            <div class="content mt-40 right">
              <h3>{{ blogs[0].title }}</h3>

              <p>{{ blogs[0].short_description }}</p>
            </div>
            <nuxt-link :to="`/blog/${blogs[0].id}`" class="read-btn float-end"
              >Continue Reading
            </nuxt-link>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AppHomeBlogs",
  props: ["blogs", "features", "testimonials"],
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
.slider-container {
  position: relative;
}
.slider-container .owl-carousel {
  background: #fff;
  padding: 30px 0px;
}
.slider-container .owl-carousel .owl-item {
  padding: 35px 15px;
}
.slider-container .owl-theme .owl-nav .owl-next,
.slider-container .owl-theme .owl-nav .owl-next:hover,
.slider-container .owl-theme .owl-nav .owl-prev,
.slider-container .owl-theme .owl-nav .owl-prev:hover {
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
.slider-container .owl-nav .owl-next {
  right: 0px;
}
.slider-container .owl-nav .owl-prev {
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
.overview-icon {
  /* height: 34px !important; */
}
.overview-icon .one {
  position: static !important;
  font-size: 23px !important;
  text-align: center;
}
.read-btn {
  color: rgb(68, 66, 66);
  text-decoration: underline !important;
}
.read-btn:hover {
  color: var(--main-color);
}
.projects-col .thumb img {
  height: 220px;
  object-fit: contain;
}
</style>
