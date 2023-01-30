<template>
  <div class="medium-bar">
    <div class="container">
      <div class="row">
        <div class="col-lg-12">
          <div class="wrapper">
            <div class="">
              <div class="bd-highlight">
                <div class="logo-box">
                  <a :href="localePath('/')"
                    ><img
                      src="/assets/images/logo.png"
                      alt="logoImage"
                      style="width: 250px"
                  /></a>
                </div>
              </div>
            </div>
            <div class="">
              <div class="ml-auto bd-highlight">
                <div class="account-cad">
                  <div class="item mb-30">
                    <div class="text">
                      <h5>GET FREE CONSULTATION!</h5>
                      <h6>
                        {{
                          $store.state.websiteSettings.find(
                            (one) => one.key === "contact_phone"
                          ).plain_value
                        }}
                      </h6>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AppMidBar",
  components: {},
  data() {
    return {};
  },
  mounted() {},
  methods: {},
};
</script>
<style scoped lang="scss">
.wrapper {
  width: 100%;
  display: flex;
  justify-content: space-between;
}
.medium-bar {
  @include md {
    display: none;
  }
}
</style>
