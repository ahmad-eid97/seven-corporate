<template>
  <div>
    <subscribe />
    <!-- Footer Style Seven Start -->
    <footer class="bg-faded pt-70 pb-40 bg-theme-color-2">
      <div class="container">
        <div class="section-content">
          <div class="row">
            <div class="col-md-3">
              <div class="footer-item footer-widget-one">
                <img
                  class="footer-logo mb-25"
                  :src="
                    $store.state.websiteSettings.find(
                      (one) => one.key === 'logo'
                    ).plain_value
                  "
                  alt="logoImage"
                />
                <p>
                  {{
                    $store.state.websiteSettings.find(
                      (one) => one.key === "description"
                    ).plain_value
                  }}
                </p>
                <hr />
              </div>
            </div>

            <div class="col-md-3">
              <div class="footer-item">
                <div class="footer-title">
                  <h4><span>CONTACT INFO</span></h4>
                </div>
                <ul class="footer-list footer-contact mb-10">
                  <li>
                    <i class="pe-7s-call"></i> Phone:
                    {{
                      $store.state.websiteSettings.find(
                        (one) => one.key === "contact_phone"
                      ).plain_value
                    }}
                  </li>
                  <li>
                    <i class="pe-7s-mail"></i>
                    Email:
                    {{
                      $store.state.websiteSettings.find(
                        (one) => one.key === "email"
                      ).plain_value
                    }}
                  </li>
                  <li>
                    <i class="pe-7s-call"></i> Address:
                    {{
                      $store.state.websiteSettings.find(
                        (one) => one.key === "contact_address"
                      ).plain_value
                    }}
                  </li>
                </ul>
              </div>
            </div>

            <div class="col-md-3">
              <div class="footer-item">
                <div class="footer-title">
                  <h4>USEFULL LINKS</h4>
                </div>
                <ul class="footer-list">
                  <!-- <li><a href="#">About Us</a></li> -->
                  <li v-for="link in $store.state.usefulLinks" :key="link.id">
                    <a :href="link.url">{{ link.name }}</a>
                  </li>
                </ul>
              </div>
            </div>

            <div class="col-md-3">
              <div class="footer-item">
                <div class="footer-title">
                  <h4>OTHER PAGES</h4>
                  <ul class="footer-list">
                    <!-- <li><a href="#">About Us</a></li> -->
                    <li v-for="page in $store.state.footerPages" :key="page.id">
                      <b-nav-item
                        :to="localePath(generatePagePath(page.id))"
                        v-if="page.status"
                        >{{ page.name }}</b-nav-item
                      >
                    </li>
                  </ul>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </footer>
    <section class="footer-copy-right bg-theme-color-2 text-white p-0">
      <div class="container">
        <div class="row">
          <div class="col-12 text-center">
            <p>
              © 2020, All Rights Reserved, Design & Developed By:<a href="#">
                Rail Coder</a
              >
            </p>
            <ul class="footer-list footer_social_links">
              <li v-for="link in $store.state.socialLinks" :key="link.key">
                <i :class="link.icon"></i>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </section>
    <!-- Footer Style Seven End -->
  </div>
</template>

<script>
import Subscribe from "../subscribe/subscribe.vue";

export default {
  name: "AppFooter",
  components: { Subscribe },
  data() {
    return {};
  },
  beforeMount() {},
  methods: {
    generatePagePath(id) {
      switch (id) {
        case 1:
          return "/about";
        case 2:
          return "/contact";
        case 3:
          return "/terms";
        case 4:
          return "/policy";
      }
    },
  },
  mounted() {
    console.log(this.$store.state.socialLinks);
  },
};
</script>

<style scoped lang="scss">
.footer-list {
  padding: 0 !important;
  li {
    color: rgb(160, 160, 160);
  }
}
.footer-title {
  margin-bottom: 0;
}
.footer_social_links {
  display: flex;
  align-items: center;
  gap: 10px;
  flex-wrap: wrap;
  justify-content: center;
  li {
    width: 35px;
    height: 35px;
    border-radius: 50%;
    box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.3);
    display: grid;
    place-content: center;
    margin: 0;
    cursor: pointer;
    padding: 0 !important;
    a {
      color: #fff;
    }
    &:hover {
      background: var(--main-color);
      color: #000 !important;
      a {
        color: #000 !important;
      }
    }
  }
}
</style>
