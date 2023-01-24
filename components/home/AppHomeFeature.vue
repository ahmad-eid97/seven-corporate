<template>
  <section class="featuresSection">
    <div class="container">
      <div
        class="row gy-4 justify-content-center"
        v-if="features.find((one) => one.key === 'features_text_list').value"
      >
        <div
          v-for="feature in features.find(
            (one) => one.key === 'features_text_list'
          ).value"
          :key="feature"
          class="col-lg-3 col-md-6 mb-10"
        >
          <div class="item" :class="$i18n.locale === 'ar' ? 'arabic' : ''">
            <div class="background">
              <h4 class="one"><i :class="feature.icon"></i></h4>
            </div>
            <div class="content">
              <h3 class="reward-h3">{{ feature.title }}</h3>
              <h6 class="reward-h6">
                {{ feature.description }}
              </h6>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AppHomeFeature",
  props: ["features"],
  components: {},
  data() {
    return {};
  },
  methods: {},
  mounted() {
    document
      .querySelector(".featuresSection")
      .style.setProperty(
        "--features-bg",
        this.features.find(
          (one) => one.key === "features_background_active_section"
        ).value === "color"
          ? this.features.find(
              (one) => one.key === "features_background_color_section"
            ).value
          : `url(${
              this.features.find(
                (one) => one.key === "features_background_image_section"
              ).value
            })`
      );

    document
      .querySelector(".featuresSection")
      .style.setProperty(
        "--features-fontSize",
        `${
          this.features.find((one) => one.key === "features_font_size_section")
            .value
        }px`
      );

    if (
      this.features.find(
        (one) => one.key === "features_border_position_section"
      ) &&
      this.features.find(
        (one) => one.key === "features_border_position_section"
      ).value === "both"
    ) {
      document
        .querySelector(".featuresSection")
        .style.setProperty(
          "--features-border-top",
          `${
            this.features.find(
              (one) => one.key === "features_border_size_section"
            ).value
          }px ${
            this.features.find(
              (one) => one.key === "features_border_type_section"
            ).value
          } ${
            this.features.find(
              (one) => one.key === "features_border_color_section"
            ).value
          }`
        );

      document
        .querySelector(".featuresSection")
        .style.setProperty(
          "--features-border-bottom",
          `${
            this.features.find(
              (one) => one.key === "features_border_size_section"
            ).value
          }px ${
            this.features.find(
              (one) => one.key === "features_border_type_section"
            ).value
          } ${
            this.features.find(
              (one) => one.key === "features_border_color_section"
            ).value
          }`
        );
    } else if (
      this.features.find(
        (one) => one.key === "features_border_position_section"
      ) &&
      this.features.find(
        (one) => one.key === "features_border_position_section"
      ).value === "top"
    ) {
      document
        .querySelector(".featuresSection")
        .style.setProperty(
          "--features-border-top",
          `${
            this.features.find(
              (one) => one.key === "features_border_size_section"
            ).value
          }px ${
            this.features.find(
              (one) => one.key === "features_border_type_section"
            ).value
          } ${
            this.features.find(
              (one) => one.key === "features_border_color_section"
            ).value
          }`
        );
    } else if (
      this.features.find(
        (one) => one.key === "features_border_position_section"
      ) &&
      this.features.find(
        (one) => one.key === "features_border_position_section"
      ).value === "bottom"
    ) {
      document
        .querySelector(".featuresSection")
        .style.setProperty(
          "--features-border-bottom",
          `${
            this.features.find(
              (one) => one.key === "features_border_size_section"
            ).value
          }px ${
            this.features.find(
              (one) => one.key === "features_border_type_section"
            ).value
          } ${
            this.features.find(
              (one) => one.key === "features_border_color_section"
            ).value
          }`
        );
    }
  },
};
</script>

<style lang="scss">
.featuresSection {
  --features-bg: #fff;
  --features-fontSize: 20px;
  --features-border-top: 0px solid #fff;
  --features-border-bottom: 0px solid #fff;

  background: var(--features-bg);
  border-top: var(--features-border-top);
  border-bottom: var(--features-border-bottom);
  background-repeat: no-repeat;
  background-size: cover;
  h3 {
    font-size: var(--features-fontSize);
  }
}
</style>
