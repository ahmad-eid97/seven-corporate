<template>
  <div class="subscribe">
    <div class="container wrapper">
      <h3>Subscribe to get in touch</h3>
      <div class="action">
        <input type="text" placeholder="Type Email" v-model="email" />
        <button @click="subscribe">Subscribe</button>
      </div>
    </div>
  </div>
</template>

<script>
import * as EmailValidator from "email-validator";

export default {
  data() {
    return {
      email: "",
    };
  },
  methods: {
    async subscribe() {
      if (!EmailValidator.validate(this.email)) {
        return this.$toast.error("Email is invalid!");
      }

      this.$store.state.showLoader = true;
      const response = await this.$axios.post("/newsletter", {
        email: this.email,
      });

      this.$store.state.showLoader = false;

      this.$toast.success("Email subscribed successfully");
    },
  },
};
</script>

<style scoped lang="scss">
.subscribe {
  background: var(--main-color);
  padding: 20px 10px;
  margin-top: 50px;
  .wrapper {
    display: flex;
    justify-content: space-between;
    align-items: center;
    .action {
      display: flex;
      align-items: center;
      input {
        border-radius: 0;
        width: 400px;
        padding: 0 15px;
        @include xs {
          width: 200px;
        }
      }
      button {
        height: 45px;
        border: none;
        background: #000;
        color: #fff;
        padding: 5px 20px;
      }
    }
    @include md {
      flex-direction: column;
    }
  }
}
</style>
