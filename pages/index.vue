<template>
  <div class="container mx-auto">
    <Jumbotron />
    <Courses />
  </div>
</template>

<script>
import Jumbotron from '~/components/Jumbotron.vue'
import Courses from '~/components/Courses.vue'

export default {
  components: { Jumbotron, Courses }
}
</script>
