<template>
  <section class="">
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
          <div class="item">
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
};
</script>
