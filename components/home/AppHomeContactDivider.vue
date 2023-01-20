<template>
  <section class="contact-divider pb-70">
    <div class="container">
      <div class="row">
        <div class="col-md-12 slide-style-center">
          <div class="contact-item">
            <h2>
              {{
                bannerTop.find((one) => one.key === "banner-top_title").value
              }}
            </h2>

            <h1>
              {{
                bannerTop
                  .find((one) => one.key === "banner-top_description")
                  .value.substring(0, 100)
              }}
            </h1>

            <div class="contact-btn-item slide-style-center mt-sm-5 mt-2">
              <a
                class="contact-btn style-1"
                href="
                  /qoutation
                "
                >Get Qoutation</a
              >
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AppHomeContactDivider",
  props: ["bannerTop"],
  components: {},
  data() {
    return {};
  },
  methods: {},
};
</script>

<style></style>
