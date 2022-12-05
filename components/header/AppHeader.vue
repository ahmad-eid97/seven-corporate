<template>
  <header class="header header-style-2 clearfix">
    <app-top-bar></app-top-bar>
    <app-mid-bar></app-mid-bar>
    <div class="menu-style bg-transparent menu-hover-2 clearfix">
      <!-- main-navigation start -->
      <div class="main-navigation main-mega-menu animated">
        <nav
          :class="{ onScroll: !topOfPage }"
          class="navbar navbar-expand-lg navbar-light"
        >
          <div class="container">
            <!-- header dropdown buttons end-->

            <b-navbar-toggle target="nav-collapse">
              <span class="navbar-toggler-icon"></span>
            </b-navbar-toggle>
            <b-collapse
              id="nav-collapse"
              is-nav
              class="collapse navbar-collapse justify-content-center"
            >
              <!-- header dropdown buttons -->
              <div class="dropdown-buttons">
                <div class="btn-group menu-search-box">
                  <b-dropdown class="menu-search-box">
                    <template #button-content>
                      <i class="fa-solid fa-magnifying-glass"></i>
                    </template>
                    <b-dropdown-form>
                      <form role="search" class="search-box">
                        <div class="form-group">
                          <input
                            type="text"
                            class="form-control"
                            placeholder="Search"
                          />
                          <i class="fa-solid fa-magnifying-glass"></i>
                          <i class="fa fa-search form-control-feedback"></i>
                        </div>
                      </form>
                    </b-dropdown-form>
                  </b-dropdown>
                </div>
              </div>
              <!-- main-menu end -->

              <!-- main-menu -->
              <ul
                class="navbar-nav align-items-end flex-lg-row-reverse flex-column-reverse pc-menu"
              >
                <!-- mega-menu end -->
                <li class="nav-item dropdown active">
                  <dropdown-menu
                    v-model="show"
                    :hover="true"
                    :closeOnClickOutside="true"
                    :hover_time="10"
                  >
                    <router-link
                      :to="localePath('/')"
                      class="nav-link dropdown-toggle"
                      data-toggle="dropdown"
                      aria-haspopup="true"
                      aria-expanded="false"
                    >
                      Home
                      <i class="fa-solid fa-angle-down"></i>
                    </router-link>
                    <div slot="dropdown">
                      <dropdown-menu
                        v-model="show6"
                        :hover="true"
                        :closeOnClickOutside="true"
                        :hover_time="10"
                      >
                        <a
                          class="dropdown-toggle dropdown-item"
                          data-toggle="dropdown"
                          href="#"
                          ><i class="fa-solid fa-angle-left"></i> Industry
                        </a>

                        <div slot="dropdown">
                          <a class="dropdown-item" href="index.html"
                            >Home style one</a
                          >
                          <a class="dropdown-item" href="index-2.html"
                            >Home style two</a
                          >
                          <a class="dropdown-item" href="index-3.html"
                            >Home style Three</a
                          >
                          <a class="dropdown-item" href="index-4.html"
                            >Home style Four</a
                          >
                        </div>
                      </dropdown-menu>
                      <dropdown-menu
                        v-model="show7"
                        :hover="true"
                        :closeOnClickOutside="true"
                        :hover_time="10"
                      >
                        <a
                          class="dropdown-toggle dropdown-item"
                          data-toggle="dropdown"
                          href="#"
                          ><i class="fa-solid fa-angle-left"></i> plumber</a
                        >

                        <div slot="dropdown">
                          <a class="dropdown-item" href="plumber-index.html"
                            >Home style one</a
                          >
                          <a class="dropdown-item" href="plumber-index-2.html"
                            >Home style two</a
                          >
                        </div>
                      </dropdown-menu>
                      <dropdown-menu
                        v-model="show8"
                        :hover="true"
                        :closeOnClickOutside="true"
                        :hover_time="10"
                      >
                        <a
                          class="dropdown-toggle dropdown-item"
                          data-toggle="dropdown"
                          href="#"
                          ><i class="fa-solid fa-angle-left"></i> cleaning</a
                        >

                        <div slot="dropdown">
                          <a class="dropdown-item" href="cleaning-index.html"
                            >cleaning style one</a
                          >
                        </div>
                      </dropdown-menu>
                      <dropdown-menu
                        v-model="show9"
                        :hover="true"
                        :closeOnClickOutside="true"
                        :hover_time="10"
                      >
                        <a
                          class="dropdown-toggle dropdown-item"
                          data-toggle="dropdown"
                          href="#"
                          ><i class="fa-solid fa-angle-left"></i> security
                          service</a
                        >

                        <div slot="dropdown">
                          <a class="dropdown-item" href="security-service.html"
                            >Home style one</a
                          >
                        </div>
                      </dropdown-menu>
                    </div>
                  </dropdown-menu>
                </li>
                <!-- mega-menu start -->

                <!-- mega-menu end -->
                <li class="nav-item dropdown">
                  <dropdown-menu
                    v-model="show1"
                    :hover="true"
                    :closeOnClickOutside="true"
                    :hover_time="10"
                  >
                    <router-link
                      :to="localePath('/about')"
                      class="nav-link dropdown-toggle"
                      data-toggle="dropdown"
                      aria-haspopup="true"
                      aria-expanded="false"
                      >ABOUT AGENCY
                      <i class="fa-solid fa-angle-down"></i>
                    </router-link>
                    <div slot="dropdown">
                      <a class="dropdown-item" href="industry-construction.html"
                        >Industry Construction</a
                      >
                      <a class="dropdown-item" href="risk-analysis.html"
                        >Risk Analysis</a
                      >
                      <a class="dropdown-item" href="industial-law.html"
                        >Industial law</a
                      >
                      <a class="dropdown-item" href="manufacturing.html"
                        >Manufacturing</a
                      >
                      <a class="dropdown-item" href="petroleum-gas.html"
                        >Petroleum and Gas</a
                      >
                      <a class="dropdown-item" href="welding-engineering.html"
                        >Welding Engineering</a
                      >
                    </div>
                  </dropdown-menu>
                </li>
                <!-- mega-menu start -->

                <!-- mega-menu end -->
                <li class="nav-item dropdown">
                  <dropdown-menu
                    v-model="show2"
                    :hover="true"
                    :closeOnClickOutside="true"
                    :hover_time="10"
                  >
                    <router-link
                      :to="localePath('/services')"
                      class="nav-link dropdown-toggle"
                      data-toggle="dropdown"
                      aria-haspopup="true"
                      aria-expanded="false"
                      >OUR SERVICES
                      <i class="fa-solid fa-angle-down"></i>
                    </router-link>
                    <div slot="dropdown">
                      <a class="dropdown-item" href="projects.html"
                        >Projects style 1</a
                      >
                      <a class="dropdown-item" href="projects-2.html"
                        >Projects style 2</a
                      >
                      <router-link class="dropdown-item" to="service"
                        >Project Details</router-link
                      >
                    </div>
                  </dropdown-menu>
                </li>
                <!-- mega-menu start -->

                <!-- mega-menu end -->
                <li class="nav-item dropdown">
                  <dropdown-menu
                    v-model="show3"
                    :hover="true"
                    :closeOnClickOutside="true"
                    :hover_time="10"
                  >
                    <nuxt-link
                      :to="localePath('/blogs')"
                      class="nav-link dropdown-toggle"
                      data-toggle="dropdown"
                      aria-haspopup="true"
                      aria-expanded="false"
                      >NEWS
                      <i class="fa-solid fa-angle-down"></i>
                    </nuxt-link>
                    <div slot="dropdown">
                      <a class="dropdown-item" href="about.html">About Us</a>
                      <a class="dropdown-item" href="team.html">Our Team</a>
                      <a class="dropdown-item" href="testimonials.html"
                        >Testimonials</a
                      >
                      <div class="dropdown">
                        <a
                          class="dropdown-toggle dropdown-item"
                          data-toggle="dropdown"
                          href="#"
                          >our services</a
                        >
                        <div class="dropdown-menu">
                          <a class="dropdown-item" href="services.html"
                            >services style one</a
                          >
                          <a class="dropdown-item" href="services-2.html"
                            >services style two</a
                          >
                        </div>
                      </div>
                      <a class="dropdown-item" href="shop.html">Shop</a>
                      <a class="dropdown-item" href="shop-single.html"
                        >Shop details</a
                      >
                      <router-link to="faq" class="dropdown-item"
                        >Faq</router-link
                      >
                      <a class="dropdown-item" href="404.html">404</a>
                    </div>
                  </dropdown-menu>
                </li>
                <!-- mega-menu start -->

                <li class="nav-item dropdown">
                  <dropdown-menu
                    v-model="show4"
                    :hover="true"
                    :closeOnClickOutside="true"
                    :hover_time="10"
                  >
                    <router-link
                      :to="localePath('/testimonials')"
                      href="blog.html"
                      class="nav-link dropdown-toggle"
                      id="seventh-dropdown"
                      data-toggle="dropdown"
                      aria-haspopup="true"
                      aria-expanded="false"
                      >TESTIMONIALS<i class="fa-solid fa-angle-down"></i>
                    </router-link>
                    <div slot="dropdown" aria-labelledby="seventh-dropdown">
                      <a class="dropdown-item" href="blog.html">Blog</a>
                      <a class="dropdown-item" href="blog-right-sidebar.html"
                        >Blog right sidebar</a
                      >
                      <a class="dropdown-item" href="blog-left-sidebar.html"
                        >Blog left sidebar</a
                      >
                      <a class="dropdown-item" href="blog-fullwidth.html"
                        >Blog full width</a
                      >
                      <a class="dropdown-item" href="blog-details.html"
                        >Blog details</a
                      >
                    </div>
                  </dropdown-menu>
                </li>

                <!-- mega-menu end -->
                <li class="nav-item dropdown">
                  <dropdown-menu
                    v-model="show5"
                    :hover="true"
                    :closeOnClickOutside="true"
                    :hover_time="10"
                  >
                    <router-link
                      :to="localePath('/contact')"
                      class="nav-link dropdown-toggle"
                      data-toggle="dropdown"
                      aria-haspopup="true"
                      aria-expanded="false"
                      >Contact <i class="fa-solid fa-angle-down"></i>
                    </router-link>
                    <div slot="dropdown">
                      <a class="dropdown-item" href="contact.html"
                        >Contact style 1</a
                      >
                      <a class="dropdown-item" href="contact-style-2.html"
                        >Contact style 2</a
                      >
                    </div>
                  </dropdown-menu>
                </li>
                <!-- mega-menu start -->
              </ul>
            </b-collapse>
            <a
              href="index.html"
              class="navbar-brand justify-content-end pc-menu"
            >
              <img
                id="logo_img"
                src="/assets/images/logo.png"
                alt="logoImage"
              />
            </a>
          </div>
        </nav>
      </div>
      <!-- main-navigation end -->
    </div>
  </header>
</template>

<script>
import AppTopBar from "./AppTopBar.vue";
import AppMidBar from "./AppMidBar.vue";
import DropdownMenu from "@innologica/vue-dropdown-menu";
export default {
  name: "AppHeader",
  components: {
    AppTopBar,
    AppMidBar,
    DropdownMenu,
  },
  data() {
    return {
      show: false,
      show1: false,
      show2: false,
      show3: false,
      show4: false,
      show5: false,
      show6: false,
      show7: false,
      show8: false,
      show9: false,
      topOfPage: true,
    };
  },
  beforeMount() {
    window.addEventListener("scroll", this.handleScroll);
  },
  mounted() {},
  methods: {
    handleScroll() {
      if (window.pageYOffset > 200) {
        if (this.topOfPage) this.topOfPage = false;
      } else {
        if (!this.topOfPage) this.topOfPage = true;
      }
    },
  },
};
</script>
<style scoped lang="scss">
.onScroll {
  position: fixed;
  width: 100%;
  height: 70px;
  display: flex;
  align-items: center;
  transition: all 0.2s ease-in-out;
  box-shadow: 0 0 10px #aaa;
  background-color: #fff;
  top: 0;
  z-index: 10;
}

.nav-item {
  i {
    max-width: 15px;
  }
}

.menu-search-box {
  ul {
    i {
      color: #fff;
      background: var(--main-color);
      top: 5px;
    }
  }
}
</style>
