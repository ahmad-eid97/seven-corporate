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

            <h1
              v-if="
                bannerTop.find((one) => one.key === 'banner-top_description')
                  .value
              "
            >
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
  mounted() {
    document
      .querySelector(".contact-divider")
      .style.setProperty(
        "--bannerTop-bg",
        this.bannerTop.find(
          (one) => one.key === "banner-top_background_active_section"
        ).value === "color"
          ? this.bannerTop.find(
              (one) => one.key === "banner-top_background_color_section"
            ).value
          : `url(${
              this.bannerTop.find(
                (one) => one.key === "banner-top_background_image_section"
              ).value
            })`
      );

    document
      .querySelector(".contact-divider")
      .style.setProperty(
        "--bannerTop-fontSize",
        `${
          this.bannerTop.find(
            (one) => one.key === "banner-top_font_size_section"
          ).value
        }px`
      );

    if (
      this.bannerTop.find(
        (one) => one.key === "banner-top_border_position_section"
      ) &&
      this.bannerTop.find(
        (one) => one.key === "banner-top_border_position_section"
      ).value === "both"
    ) {
      document
        .querySelector(".contact-divider")
        .style.setProperty(
          "--bannerTop-border-top",
          `${
            this.bannerTop.find(
              (one) => one.key === "banner-top_border_size_section"
            ).value
          }px ${
            this.bannerTop.find(
              (one) => one.key === "banner-top_border_type_section"
            ).value
          } ${
            this.bannerTop.find(
              (one) => one.key === "banner-top_border_color_section"
            ).value
          }`
        );

      document
        .querySelector(".contact-divider")
        .style.setProperty(
          "--bannerTop-border-bottom",
          `${
            this.bannerTop.find(
              (one) => one.key === "banner-top_border_size_section"
            ).value
          }px ${
            this.bannerTop.find(
              (one) => one.key === "banner-top_border_type_section"
            ).value
          } ${
            this.bannerTop.find(
              (one) => one.key === "banner-top_border_color_section"
            ).value
          }`
        );
    } else if (
      this.bannerTop.find(
        (one) => one.key === "banner-top_border_position_section"
      ) &&
      this.bannerTop.find(
        (one) => one.key === "banner-top_border_position_section"
      ).value === "top"
    ) {
      document
        .querySelector(".contact-divider")
        .style.setProperty(
          "--bannerTop-border-top",
          `${
            this.bannerTop.find(
              (one) => one.key === "banner-top_border_size_section"
            ).value
          }px ${
            this.bannerTop.find(
              (one) => one.key === "banner-top_border_type_section"
            ).value
          } ${
            this.bannerTop.find(
              (one) => one.key === "banner-top_border_color_section"
            ).value
          }`
        );
    } else if (
      this.bannerTop.find(
        (one) => one.key === "banner-top_border_position_section"
      ) &&
      this.bannerTop.find(
        (one) => one.key === "banner-top_border_position_section"
      ).value === "bottom"
    ) {
      document
        .querySelector(".contact-divider")
        .style.setProperty(
          "--bannerTop-border-bottom",
          `${
            this.bannerTop.find(
              (one) => one.key === "banner-top_border_size_section"
            ).value
          }px ${
            this.bannerTop.find(
              (one) => one.key === "banner-top_border_type_section"
            ).value
          } ${
            this.bannerTop.find(
              (one) => one.key === "banner-top_border_color_section"
            ).value
          }`
        );
    }
  },
};
</script>

<style lang="scss">
.contact-divider {
  --bannerTop-bg: #fff;
  --bannerTop-fontSize: 20px;
  --bannerTop-border-top: 0px solid #fff;
  --bannerTop-border-bottom: 0px solid #fff;

  background: var(--bannerTop-bg);
  border-top: var(--bannerTop-border-top);
  border-bottom: var(--bannerTop-border-bottom);
  background-repeat: no-repeat;
  background-size: cover;
  h1 {
    font-size: var(--bannerTop-fontSize);
  }
}
</style>
