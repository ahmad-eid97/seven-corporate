<template>
  <div class="home">
        <!-- Slick Section Start -->
        <app-home-slider :sliderData="sliderData"></app-home-slider>
        <!-- Slick Section End -->
        
        <app-home-feature></app-home-feature>

        <app-home-blogs></app-home-blogs>

        <app-home-contact-divider></app-home-contact-divider>

        <!-- WHY WORK WITH US Start -->
        <app-home-why></app-home-why>
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
import AppHomeBlogs from '../components/home/AppHomeBlogs.vue'
import AppHomeContactDivider from '../components/home/AppHomeContactDivider.vue'
import AppHomeFeature from '../components/home/AppHomeFeature.vue'
import AppHomeNews from '../components/home/AppHomeNews.vue'
import AppHomeServices from '../components/home/AppHomeServices.vue'
import AppHomeServicesOffers from '../components/home/AppHomeServicesOffers.vue'
import AppHomeSlider from '../components/home/AppHomeSlider.vue'
import AppHomeTestimonials from '../components/home/AppHomeTestimonials.vue'
import AppHomeWhy from '../components/home/AppHomeWhy.vue'
// @ is an alias to /src

export default {
  name: 'Home',
  components: {
    AppHomeSlider,
    AppHomeFeature,
    AppHomeBlogs,
    AppHomeContactDivider,
    AppHomeWhy,
    AppHomeServices,
    AppHomeTestimonials,
    AppHomeNews,
    AppHomeServicesOffers
  },
  async asyncData({ $axios }) {
    const sliderData = await $axios.get('/sliders');
    
    const services = await $axios.get('/services');

    const testimonials = await $axios.get('/testimonials');

    const blogs = await $axios.get('/blogs?latest=1');

    return {
      sliderData: sliderData.data.data.sliders,
      services: services.data.data.services,
      testimonials: testimonials.data.data.testimonials,
      blogs: blogs.data.data.blogs,
    }
  }
}
</script>
