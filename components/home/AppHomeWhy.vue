<template>
  <section class="bg-f9 whySection">
    <div class="container">
      <div class="row">
        <div class="section-title">
          <h2>WHY WORK WITH US</h2>
        </div>
      </div>
      <div class="row gy-4 justify-content-center align-items-center">
        <div class="col-lg-6">
          <div
            class="aboutus"
            v-if="
              features.find((one) => one.key === 'features_text_list').value
            "
          >
            <h3>5 MAIN REASONS TO CHOOSE US</h3>
            <div
              v-for="(feature, index) in features.find(
                (one) => one.key === 'features_text_list'
              ).value"
              :key="index"
              class="about-item mb-20"
            >
              <div class="about-icon">
                <img
                  :src="`/assets/images/icons/${index + 1}.png`"
                  alt="icon"
                />
              </div>
              <div class="about-details">
                <p>{{ feature.description }}</p>
              </div>
            </div>
          </div>
        </div>

        <div class="col-auto">
          <div class="about-us">
            <div class="about-us-list">
              <div
                class="about-us-icon-a about-us-icon"
                :class="show == 'show1' ? 'active' : ''"
              >
                <h4 class="one" @click="showData('show1')">
                  <i class="fa-solid fa-user-tie"></i>
                </h4>
              </div>
              <div
                class="about-us-icon-b about-us-icon"
                :class="show == 'show2' ? 'active' : ''"
              >
                <h4 class="one" @click="showData('show2')">
                  <i class="fa-solid fa-gears"></i>
                </h4>
              </div>
              <div
                class="about-us-icon-c about-us-icon"
                :class="show == 'show3' ? 'active' : ''"
              >
                <h4 class="one" @click="showData('show3')">
                  <i class="fa-solid fa-comments"></i>
                </h4>
              </div>
              <div
                class="about-us-icon-d about-us-icon"
                :class="show == 'show4' ? 'active' : ''"
              >
                <h4 class="one" @click="showData('show4')">
                  <i class="fa-solid fa-flag"></i>
                </h4>
              </div>
              <div
                class="about-us-icon-e about-us-icon"
                :class="show == 'show5' ? 'active' : ''"
              >
                <h4 class="one" @click="showData('show5')">
                  <i class="fa-solid fa-briefcase"></i>
                </h4>
              </div>
            </div>
            <div
              class="about-us-main"
              v-if="
                features.find((one) => one.key === 'features_text_list').value
              "
            >
              <h4
                v-for="(feature, index) in features
                  .find((one) => one.key === 'features_text_list')
                  .value.slice(0, 5)"
                :key="index"
                class="about-us-main-icon"
              >
                <div
                  v-if="show == `show${index + 1}`"
                  class="about-us-main-content"
                >
                  <i class="fa-solid fa-user-tie"></i>
                  <h2>
                    {{ feature.title }}
                  </h2>

                  <p>
                    {{ feature.description }}
                  </p>
                </div>
              </h4>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AppHomeWhy",
  props: ["features"],
  components: {},
  data() {
    return {
      show: "show1",
    };
  },
  mounted() {
    this.autoPlay();
    document
      .querySelector(".whySection")
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
      .querySelector(".whySection")
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
        .querySelector(".whySection")
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
        .querySelector(".whySection")
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
        .querySelector(".whySection")
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
        .querySelector(".whySection")
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
  methods: {
    autoPlay() {
      var items = ["show1", "show2", "show3", "show4", "show5"];
      var item = "";
      let _this = this;
      setInterval(function () {
        item = items[Math.floor(Math.random() * items.length)];
        _this.showData(item);
      }, 5000);
    },
    showData(show) {
      this.show = show;
    },
  },
};
</script>

<style lang="scss">
.whySection {
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
  p {
    font-size: 0.9rem;
    opacity: 0.8;
  }
}
p {
  margin-left: 0 !important;
}
.about-us {
  height: 442px !important;
  width: 452px !important;
  max-width: 450px !important;
}
.aboutus {
  margin: 0 20px;
}
.about-us .one {
  font-size: 25px !important;
  padding: 5px !important;
}
.about-us-icon-a {
  top: -220px !important;
}
.about-us-icon-b {
  left: 210.743px !important;
}
.about-us-icon-c {
  left: 125.191px !important;
  top: 182.074px !important;
}
.about-us-icon-d {
  left: -125.191px !important;
  top: 182.074px !important;
}
.about-us-icon-e {
  left: -210.743px !important;
}
.about-us-main-icon {
  margin-top: 50px;
}
.about-icon {
  width: 30px !important;
  height: 30px !important;
  margin-left: 0 !important;
}
.about-icon img {
  width: 30px !important;
  height: 30px !important;
}
.about-item {
  gap: 20px !important;
}
.about-us-icon.active {
  animation-name: circle_pop;
  -webkit-animation-duration: 1.5s;
  animation-duration: 1.5s;
  -webkit-animation-timing-function: linear;
  animation-timing-function: linear;
  -webkit-animation-iteration-count: infinite;
  animation-iteration-count: infinite;
}
@keyframes circle_pop {
  0%,
  100% {
    transform: scale3d(1, 1, 1);
  }
  50% {
    transform: scale3d(1.3, 1.3, 1.3);
  }
}
</style>
