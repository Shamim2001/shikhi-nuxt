<template>
  <div class="col-md-4 mb-4">
    <div class="shikhi__courses_card">
      <div class="card courses_card">
        <nuxt-link :to="'course/' + course.slug"
          ><img :src="course.thumbnail" class="card-img-top" alt="" /></nuxt-link>
        <div class="">
          <a href="#" class="wishlist_icon">
            <i class="fa fa-bookmark-o"></i>
          </a>
        </div>
        <div class="card-body">
          <div class="courses__card_rating">
            <div class="rating">
              <i class="fa fa-star-o"></i>
              <i class="fa fa-star-o"></i>
              <i class="fa fa-star-o"></i>
              <i class="fa fa-star-o"></i>
              <i class="fa fa-star-o"></i>
              <span>5.00 (7)</span>
            </div>
          </div>
          <h5 class="card-title">{{ course?.name }}</h5>
          <div class="card-text">
            <div class="card-icon">
              <span><i class="fa fa-user-o"></i>816</span>
              <span><i class="fa fa-user-o"></i>2h 23m</span>
            </div>

            <div class="author">
              <a class="authon_icon" href="single.html">sa</a>
              <div class="">
                by <a href="single.html" class="author_name">Shamim Ahmed</a>
              </div>
            </div>
          </div>
        </div>
        <div class="courses__card_btn">
          <nuxt-link
            :to="'course/' + course.slug"
            class="shikhi__btn shikhi__btn_primary"
            >View Details
          </nuxt-link>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    course: [],
  },
};
</script>

<style></style>
