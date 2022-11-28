<template>
  <section class="shikhi__courses_area">
    <div class="container">
      <div class="row">
        <div class="col-sm-12">
          <div class="courses_text">
            <h2>Courses</h2>
          </div>
        </div>
      </div>
      <!-- .row -->

      <div class="row gy-4">
        <CourseCard v-for="course in courses" :key="course.id" :course="course" />
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "IndexPage",
  auth: false,
  data() {
    return {
      courses: []
    }
  },
  mounted () {
    this.getCourses()
  },
  methods: {
    async getCourses() {
      const res = await this.$axios.get('/courses').then((res)=> {

        if (res.data.error) {
          this.courses = res.data.courses

        }
      })
    }
  },

};
</script>
