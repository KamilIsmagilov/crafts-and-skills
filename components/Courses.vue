<template>
  <div class="mt-32 mb-32">
    <div class="text-5xl text-center">
      Courses
    </div>
    <NuxtLink
      to="/course/vue-basic"
      class="block w-56 h-64 bg-red-300"
      v-for="(course, idx) in allCourses"
      :key="idx">
        <img :src="course.imgSrc" :alt="course.title" class="bg-cover">
    </NuxtLink>
  </div>
</template>

<script>
import firebase from 'firebase'
const db = firebase.firestore()

export default {
  name: 'Courses',
  data () {
    return {
      allCourses: []
    }
  },
  created () {
    db.collection('courses')
      .where('isActive', '==', true)
      .get()
      .then((querySnapshot) => {
        this.allCourses = querySnapshot.docs.map(doc => doc.data())
      })
  }
}
</script>
