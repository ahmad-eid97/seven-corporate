<template>
  <div class="home">
    <!-- Slick Section Start -->
    <app-home-slider :slides="slides"></app-home-slider>
    <!-- Slick Section End -->

    <app-home-feature :features="features"></app-home-feature>

    <app-home-blogs
      :blogs="blogs.slice(0, 1)"
      :features="features"
      :testimonials="testimonials"
    ></app-home-blogs>

    <app-home-contact-divider :bannerTop="bannerTop"></app-home-contact-divider>

    <!-- WHY WORK WITH US Start -->
    <app-home-why :features="features"></app-home-why>
    <!-- WHY WORK WITH US End -->

    <!-- SERVICES WE PROVIDESection Start -->
    <app-home-services :services="services"></app-home-services>
    <!-- SERVICES WE PROVIDE Section End -->

    <!-- testimonials Section Start -->
    <app-home-testimonials :testimonials="testimonials"></app-home-testimonials>
    <!-- testimonials Section End -->

    <app-home-news :blogs="blogs"></app-home-news>

    <!-- Services Section Start -->
    <app-home-services-offers></app-home-services-offers>
  </div>
</template>

<script>
import AppHomeBlogs from "../components/home/AppHomeBlogs.vue";
import AppHomeContactDivider from "../components/home/AppHomeContactDivider.vue";
import AppHomeFeature from "../components/home/AppHomeFeature.vue";
import AppHomeNews from "../components/home/AppHomeNews.vue";
import AppHomeServices from "../components/home/AppHomeServices.vue";
import AppHomeServicesOffers from "../components/home/AppHomeServicesOffers.vue";
import AppHomeSlider from "../components/home/AppHomeSlider.vue";
import AppHomeTestimonials from "../components/home/AppHomeTestimonials.vue";
import AppHomeWhy from "../components/home/AppHomeWhy.vue";
// @ is an alias to /src

export default {
  name: "Home",
  components: {
    AppHomeSlider,
    AppHomeFeature,
    AppHomeBlogs,
    AppHomeContactDivider,
    AppHomeWhy,
    AppHomeServices,
    AppHomeTestimonials,
    AppHomeNews,
    AppHomeServicesOffers,
  },
  async asyncData({ $axios, app }) {
    const slides = await $axios.get("/sliders", {
      headers: {
        "Accept-Language": app.i18n.locale,
      },
    });

    const features = await $axios.get("/sections/features", {
      headers: {
        "Accept-Language": app.i18n.locale,
      },
    });

    const bannerTop = await $axios.get("/sections/banner-top", {
      headers: {
        "Accept-Language": app.i18n.locale,
      },
    });

    const services = await $axios.get("/services");

    const testimonials = await $axios.get("/testimonials");

    const blogs = await $axios.get("/blogs?latest=1");

    return {
      slides: slides.data.data.sliders,
      features: features.data.data,
      bannerTop: bannerTop.data.data,
      services: services.data.data.services,
      testimonials: testimonials.data.data.testimonials,
      blogs: blogs.data.data.blogs.slice(0, 5),
    };
  },
};
</script>
