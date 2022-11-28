<template>
  <div class="col-4 mx-auto my-5 py-2 border shadow-lg rounded">
    <h2 class="card-title">Login</h2>
    <form action="" @submit.prevent="handleLogin" method="post" class="">
      <div class="mt-3">
        <label for="email">Email</label>
        <input
          type="email"
          id="email"
          v-model="form.email"
          class="form-control"
          placeholder=""
          autocomplete="off"
          value="admin@shikhi.test"
        />
      </div>
      <div class="mt-3">
        <label for="password">Password</label>
        <input
          type="password"
          id="password"
          v-model="form.password"
          class="form-control"
          autocomplete="false"
          value="123"
        />
      </div>
      <div class="mt-3">
        <button
          type="submit"
          class="btn btn-primary text-end"
          :disabled="!form.email || !form.password"
        >
          Login
        </button>
      </div>
      <div class="mt-2 text-center">
        <nuxt-link to="/">Back to site</nuxt-link>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        email: "admin@shikhi.test",
        password: "123",
      },
    };
  },
  methods: {
    async handleLogin() {
      this.$auth.loginWith("laravelSanctum", {
        data: this.form
      });
    },
  },
};
</script>

<style>
</style>
