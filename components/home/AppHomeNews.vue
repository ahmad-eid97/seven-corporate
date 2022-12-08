<template>
  <section class="blog-section">
    <div class="container">
      <div class="row">
        <div class="section-title">
          <h2>RECENT NEWS & EVENTS</h2>
        </div>
      </div>
      <div class="row">
        <div class="col-md-6 col-lg-4 news-carousel">
          <swiper
            :options="swiperOption"
            class="owl-carousel"
            v-if="blogs.length >= 1"
          >
            <swiper-slide v-for="blog in blogs.slice(0, 2)" :key="blog.id">
              <div class="item">
                <div class="events-col">
                  <div class="thumb">
                    <img :src="blog.image" :alt="blog.title" />
                  </div>
                  <div class="content">
                    <h3>{{ blog.publish_date }} / {{ blog.username }}</h3>
                    <h4>{{ blog.title }}</h4>

                    <h6>{{ blog.short_description }}</h6>
                    <nuxt-link :to="`/blog/${blog.id}`" class="btn"
                      >VIEW DETAILS</nuxt-link
                    >
                  </div>
                </div>
              </div>
            </swiper-slide>

            <div class="swiper-button-next" slot="button-next"></div>
            <div class="swiper-button-prev" slot="button-prev"></div>
          </swiper>
        </div>
        <div class="col-md-6 col-lg-8">
          <div class="row" v-if="blogs.length >= 1">
            <div
              v-for="blog in blogs.slice(2, blogs.length)"
              :key="blog.id"
              class="col-lg-4"
            >
              <div class="events">
                <div class="thumb">
                  <img :alt="blog.title" :src="blog.image" />
                </div>

                <div class="content mt-40 right">
                  <h3>{{ blog.title }}</h3>

                  <p>{{ blog.short_description }}</p>
                </div>
                <nuxt-link :to="`/blog/${blog.id}`" class="read-btn float-end"
                  >Read more
                  <i class="fa-solid fa-caret-right"></i>
                </nuxt-link>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AppHomeNews",
  props: ["blogs"],
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

<style lang="scss" scoped>
.events .svg-inline--fa {
  vertical-align: -2px;
}
.news-carousel {
  position: relative;
}
.news-carousel .owl-carousel {
  background-color: #f5f5f5;
  padding: 30px 0;
}
.news-carousel .owl-carousel .owl-item {
  padding: 35px 35px;
}
.news-carousel .btn,
.news-carousel .btn:hover {
  background-color: var(--main-color);
  border-radius: 0;
  color: #fff;
  padding: 10px 16px;
  font-weight: bold;
  border: none;
}
.thumb img {
  height: 250px;
}
.news-carousel .owl-theme .owl-nav .owl-next,
.news-carousel .owl-theme .owl-nav .owl-next:hover,
.news-carousel .owl-theme .owl-nav .owl-prev,
.news-carousel .owl-theme .owl-nav .owl-prev:hover {
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
.news-carousel .owl-nav .owl-next {
  right: 0px;
}
.news-carousel .owl-nav .owl-prev {
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

a {
  color: rgb(150, 150, 150);
  &:hover {
    color: var(--main-color);
  }
}
</style>
