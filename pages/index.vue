<template>
  <div class="home">
    <!-- Slick Section Start -->
    <app-home-slider :slides="slides"></app-home-slider>

    <app-home-partners :partners="partners" />
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

    <app-home-activities :activities="activities" />

    <app-home-steps :steps="steps" />

    <!-- Services Section Start -->
    <app-home-services-offers></app-home-services-offers>
    <SocialChat :attendants="attendants">
      <p slot="header">Click one of our representatives below to chat.</p>
      <template v-slot:button="{ open }">
        <span v-show="!open">Contact us</span>
        <span v-show="open">Close</span>
      </template>
      <small slot="footer">Opening hours: 8am to 10pm</small>
    </SocialChat>
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
import AppHomeActivities from "../components/home/AppHomeActivities.vue";
import AppHomeSteps from "../components/home/AppHomeSteps.vue";
import AppHomePartners from "../components/home/AppHomePartners.vue";
// @ is an alias to /src

export default {
  name: "Home",
  data() {
    return {
      attendants: [
        {
          app: "whatsapp",
          label: "Support",

          name: this.$store.state.websiteSettings.find(
            (one) => one.key === "chat_widget_whatsapp_label"
          )
            ? this.$store.state.websiteSettings.find(
                (one) => one.key === "chat_widget_whatsapp_label"
              ).plain_value
            : "Laravada",

          number: this.$store.state.websiteSettings.find(
            (one) => one.key === "chat_widget_whatsapp_number"
          )
            ? this.$store.state.websiteSettings.find(
                (one) => one.key === "chat_widget_whatsapp_number"
              ).plain_value
            : "11111111111",

          avatar: {
            src: "https://avatars0.githubusercontent.com/u/8084606?s=460&u=20b6499a416cf7129a18e5c168cf387e159edb1a&v=4",
            alt: "Laravada customer support",
          },
        },
        {
          app: "messenger",
          label: "Technical support",

          name: this.$store.state.websiteSettings.find(
            (one) => one.key === "chat_widget_messenger_label"
          )
            ? this.$store.state.websiteSettings.find(
                (one) => one.key === "chat_widget_messenger_label"
              ).plain_value
            : "Laravada Facebook",

          id: this.$store.state.websiteSettings.find(
            (one) => one.key === "chat_widget_messenger_id"
          )
            ? this.$store.state.websiteSettings.find(
                (one) => one.key === "chat_widget_messenger_id"
              ).plain_value
            : "111111111111",

          avatar: {
            src: "https://avatars0.githubusercontent.com/u/8084606?s=460&u=20b6499a416cf7129a18e5c168cf387e159edb1a&v=4",
            alt: "Laravada customer support",
          },
        },
      ],
    };
  },
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
    AppHomeActivities,
    AppHomeSteps,
    AppHomePartners,
  },
  async asyncData({ $axios, app }) {
    const slides = await $axios.get("/sliders", {
      headers: {
        "Accept-Language": app.i18n.locale,
      },
    });

    const partners = await $axios.get("/partners");

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

    const activities = await $axios.get("/sections/activities", {
      headers: {
        "Accept-Language": app.i18n.locale,
      },
    });

    const steps = await $axios.get("/sections/steps", {
      headers: {
        "Accept-Language": app.i18n.locale,
      },
    });

    return {
      slides: slides.data.data.sliders,
      partners: partners.data.data.partners,
      features: features.data.data,
      bannerTop: bannerTop.data.data,
      services: services.data.data.services,
      testimonials: testimonials.data.data.testimonials,
      blogs: blogs.data.data.blogs.slice(0, 5),
      activities: activities.data.data,
      steps: steps.data.data,
    };
  },
  mounted() {},
};
</script>

<style lang="scss">
.home {
  --vsc-bg-header: var(--main-color);
  --vsc-bg-footer: var(--main-color);
  --vsc-text-color-header: #000;
  --vsc-text-color-footer: #000;
  --vsc-bg-button: var(--main-color);
  --vsc-text-color-button: #000;
  --vsc-outline-color: var(--main-color);
  --vsc-border-color-bottom-header: #fff;
  --vsc-border-color-top-footer: #fff;
}
</style>
