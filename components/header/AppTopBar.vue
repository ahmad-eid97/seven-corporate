<template>
  <div class="top-bar">
    <div class="container">
      <div class="row m-0">
        <div class="col-lg-12">
          <div class="d-flex justify-content-between align-items-center">
            <div class="col-auto">
              <div class="float-right">
                <ul class="social-icon bordered-theme">
                  <li>
                    <a href="#">
                      <i class="fa-brands fa-facebook-f"></i>
                    </a>
                  </li>
                  <li>
                    <a href="#"><i class="fa-brands fa-twitter"></i> </a>
                  </li>
                  <li>
                    <a href="#"><i class="fa-brands fa-linkedin-in"></i> </a>
                  </li>
                  <li>
                    <a href="#"><i class="fa-solid fa-wifi"></i></a>
                  </li>
                  <li>
                    <a href="#"><i class="fa-brands fa-youtube"></i> </a>
                  </li>
                </ul>
              </div>
            </div>
            <div class="col-auto">
              <div class="d-flex" style="gap: 25px">
                <lang-switch></lang-switch>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import LangSwitch from "../langSwitch/langSwitch.vue";
export default {
  name: "AppTopBar",
  components: {
    LangSwitch,
  },
  data() {
    return {};
  },
  mounted() {},
  methods: {},
};
</script>
<style scoped lang="scss">
.top-bar {
  height: 55px;
  .social-icon {
    margin: 0;
    li {
      i {
        max-width: 20px;
      }
    }
  }
  ul {
    padding: 0;
  }
  .p-content {
    margin: 0;
    @include xs {
      display: none;
    }
  }
}
</style>
