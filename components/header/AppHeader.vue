<template>
  <header class="header header-style-2 clearfix">
    <div class="cart" :class="openCart ? 'opened' : ''">
      <div class="head">
        <i class="fa-regular fa-xmark" @click="openCart = false"></i>
        <button
          @click="goToCheckout"
          :disabled="$store.state.cartItems.length <= 0"
        >
          <i class="fa-regular fa-badge-check"></i> Checkout
        </button>
      </div>
      <cart />
    </div>
    <app-top-bar></app-top-bar>
    <app-mid-bar></app-mid-bar>
    <div class="menu-style bg-transparent menu-hover-2 clearfix">
      <!-- main-navigation start -->
      <div class="main-navigation main-mega-menu animated">
        <nav
          :class="{ onScroll: !topOfPage }"
          class="navbar navbar-expand-lg navbar-light"
        >
          <div
            class="container header_container d-flex align-items-center justify-content-between"
          >
            <!-- header dropdown buttons end-->
            <div>
              <a
                :href="localePath('/')"
                class="navbar-brand justify-content-end pc-menu"
              >
                <img
                  id="logo_img"
                  src="/assets/images/logo.png"
                  alt="logoImage"
                />
              </a>
            </div>
            <div class="d-flex align-items-center smallScr">
              <div class="m-0 cartIcon" @click="openCart = !openCart">
                <span>{{ $store.state.cartItems.length }}</span>
                <i class="fa-regular fa-cart-plus"></i>
              </div>
              <div v-if="$store.state.user" class="logout" @click="logout">
                <i class="fa-regular fa-right-from-bracket"></i>
              </div>
              <b-navbar-toggle target="nav-collapse">
                <span class="navbar-toggler-icon"></span>
              </b-navbar-toggle>
            </div>
          </div>

          <b-collapse
            id="nav-collapse"
            is-nav
            class="collapse navbar-collapse justify-content-end"
          >
            <!-- main-menu -->

            <b-navbar-nav class="align-items-center">
              <b-nav-item
                active-class="active"
                :to="localePath(`/${item.link}`)"
                exact
                v-for="item in $store.state.topMenu"
                :key="item.id"
              >
                <span v-if="!item.child.length">{{ item.label }}</span>

                <b-dropdown
                  :text="item.label"
                  block
                  class="dropdownBtn"
                  v-if="item.child.length"
                  variant="span"
                  size="lg"
                >
                  <b-dropdown-item
                    v-for="child in item.child"
                    :key="child.id"
                    :to="localePath('/' + child.link)"
                    >{{ child.label }}</b-dropdown-item
                  >
                </b-dropdown>
              </b-nav-item>
              <b-nav-item
                v-if="$store.state.user"
                @click="logout"
                class="outLarge"
              >
                Logout
              </b-nav-item>
            </b-navbar-nav>

            <div class="dropdown-buttons">
              <div
                class="btn-group menu-search-box"
                :class="$i18n.locale === 'ar' ? 'arabic' : ''"
              >
                <b-dropdown
                  class="menu-search-box"
                  :class="$i18n.locale === 'ar' ? 'arabic' : ''"
                >
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
                      </div>
                    </form>
                  </b-dropdown-form>
                </b-dropdown>
              </div>
            </div>
          </b-collapse>
          <div class="d-flex align-items-center largeScr">
            <div class="m-0 cartIcon" @click="openCart = !openCart">
              <span>{{ $store.state.cartItems.length }}</span>
              <i class="fa-regular fa-cart-plus"></i>
            </div>
            <div v-if="$store.state.user" class="logout" @click="logout">
              <i class="fa-regular fa-right-from-bracket"></i>
            </div>
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
import cart from "../cart/cart.vue";
export default {
  name: "AppHeader",
  components: {
    AppTopBar,
    AppMidBar,
    DropdownMenu,
    cart,
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
      openCart: false,
    };
  },
  beforeMount() {
    window.addEventListener("scroll", this.handleScroll);
  },
  mounted() {},
  methods: {
    logout() {
      this.$swal({
        title: "Logout!",
        text: "Are you sure? You want to logout from your account!",
        type: "warning",
        showCancelButton: true,
        confirmButtonColor: "#ff5e57",
        confirmButtonText: "Logout",
      }).then((result) => {
        if (result.value) {
          this.confirmLogout();
        }
      });
    },
    confirmLogout() {
      this.$store.commit("setUserData", null);
      this.$cookies.remove("cms-auth");
      this.$cookies.remove("cms-user");
      this.$router.push(this.localePath("/login"));
    },
    handleScroll() {
      if (window.pageYOffset > 200) {
        if (this.topOfPage) this.topOfPage = false;
      } else {
        if (!this.topOfPage) this.topOfPage = true;
      }
    },
    goToCheckout() {
      this.openCart = false;
      this.$router.push("/checkout");
    },
  },
};
</script>
<style scoped lang="scss">
.swal2-container {
  padding: 0 !important;
}
.swal2-shown {
  padding: 0 !important;
}
.swal2-confirm,
.swal2-cancel {
  box-shadow: none !important;
}
.swal2-confirm:focus,
.swal2-cancel:focus {
  box-shadow: none !important;
}
.swal2-cancel {
  background: #e5e5e5 !important;
  color: rgb(51, 51, 51) !important;
}
.navbar {
  padding: 10px 20px;
}
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
.cart {
  width: 390px;
  height: 100vh;
  position: fixed;
  top: 0;
  right: 0;
  transform: translateX(390px);
  background-color: #fff;
  z-index: 999999;
  box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.2);
  @include xs {
    width: 350px;
  }
  .head {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 10px;
    & > i {
      border: 1px solid var(--main-color);
      border-radius: 5px;
      width: 30px;
      height: 30px;
      display: grid;
      place-items: center;
      cursor: pointer;
      background-color: var(--main-color);
      color: #fff;
      &:hover {
        color: var(--main-color);
        background: transparent;
      }
    }
    button {
      padding: 5px 30px;
      font-size: 1.1rem;
      background-color: var(--main-color);
      color: #fff;
      border: 1px solid var(--main-color);
      display: flex;
      align-items: center;
      gap: 5px;
      i {
        font-size: 1.1rem;
      }
      &:disabled {
        opacity: 0.5;
        cursor: not-allowed;
        &:hover {
          background-color: var(--main-color);
          color: #fff;
        }
      }
      &:hover {
        background-color: transparent;
        color: var(--main-color);
      }
    }
  }
  &.opened {
    transform: translateX(0);
  }
}
.cartIcon {
  border: 1px solid var(--main-color);
  border-radius: 5px;
  width: 45px;
  height: 45px;
  display: grid;
  place-items: center;
  cursor: pointer;
  position: relative;
  margin: 0 15px !important;
  span {
    position: absolute;
    top: -15px;
    right: -10px;
    width: 30px;
    height: 30px;
    background-color: var(--main-color);
    border-radius: 50%;
    color: #fff;
    display: grid;
    place-content: center;
    font-size: 1.2rem;
    @include sm {
      font-size: 1rem;
    }
  }
  i {
    color: var(--main-color);
  }
  @include sm {
    width: 40px;
    height: 40px;
    margin: 0 10px !important;
  }
  &:hover {
    background-color: var(--main-color);
    border-color: var(--main-color);
    i {
      color: #fff;
    }
  }
}
.navbar-toggler {
  box-shadow: none !important;
  margin: 0;
}
.logout {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background-color: var(--main-color);
  color: #fff;
  display: grid;
  place-items: center;
  font-size: 1.2rem;
  cursor: pointer;
  @include md {
    display: none;
  }
}

.outLarge {
  display: none;
  @include md {
    display: inline;
  }
}
.smallScr {
  align-items: center;
  display: none !important;
  @include md {
    display: flex !important;
  }
}
.largeScr {
  align-items: center;
  display: flex !important;
  @include md {
    display: none !important;
  }
}
.header_container {
  display: flex;
  justify-content: center;
}

.nav-item {
  i {
    max-width: 15px;
  }
  & > .dropdown {
    display: none;
  }
}
.form-control:focus {
  box-shadow: 0 0 0 0.05rem rgb(13 110 253 / 25%) !important;
}

.form-group {
  display: flex;
  i {
    color: #fff;
    background: var(--main-color);
    top: 5px;
    width: 50px;
    display: grid;
    place-content: center;
    font-size: 1.3rem;
  }
}
.navbar-brand {
  margin: 0 !important;
  img {
    min-height: 20px;
  }
}
.nav-link {
  font-size: 1.1rem;
  text-transform: none !important;
  position: relative;
  top: 3px;
  padding: 5px 20px !important;
}
.dropdownBtn {
  margin: 0 !important;
  button {
    background: none !important;
    padding: 0 !important;
    text-transform: uppercase !important;
    font-size: 1.2rem !important;
    font-family: unset !important;
    font-weight: 400 !important;
    box-shadow: none !important;
    border: none !important;
    min-width: 60px !important;
    position: relative;
    top: -3px;
  }
  .dropdown-menu {
    top: 40px !important;
  }
}
</style>
