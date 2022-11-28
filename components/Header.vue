<template>
  <section class="shikhi__header_area">
    <div class="container">
      <div class="row">
        <div class="col col-auto my-auto">
          <div class="shikhi__header_logo">
            <nuxt-link to="/">Shikhi</nuxt-link>
          </div>
        </div>
        <div class="col my-auto" style="text-align: right;">
          <div class="shikhi__header_menu">
            <ul>
              <li class="nav-link" v-if="$auth.loggedIn">
                <p>{{ $auth.user.name }}</p>
              </li>
              <li class="nav-link" v-if="!$auth.loggedIn">
                <nuxt-link to="/login">Login</nuxt-link>
                </li>
              <li>
                <nuxt-link to="/">Courses</nuxt-link>
              </li>
              <li class="nav-link" v-if="$auth.loggedIn">
                <button type="button" @click.prevent="logout">log out</button>
                </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
  <!-- .shikhi__header_area -->
</template>

<script>
export default {
  methods: {
    logout() {
      this.$auth.logout();
    }
  },

}
</script>

<style>

</style>
