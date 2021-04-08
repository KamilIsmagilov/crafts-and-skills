<template>
  <div>
    <div class="flex w-screen bg-red-300 h-screen">
      <div class="w-64 h-screen bg-gray-300">
        <div class="">{{ this.course.name }}</div>
        <div class="">
          <NuxtLink v-for="(lesson, idx) in this.course.lessons" :key="idx" :to="`/course/vue-basic/${lesson.lessonSlug}`"
            class="block bg-yellow-500 p-4">
            {{ lesson.title }}
          </NuxtLink>
        </div>
      </div>
      <Nuxt />
    </div>
  </div>
</template>

<script>
import firebase from 'firebase'
const db = firebase.firestore()

export default {
  async asyncData ({ params }) {
    const slug = params.slug
    const query = await db.collection('courses')
      .where('slug', '==', slug)
      .limit(1)
      .get()
    if (!query.empty) {
      const snapshot = query.docs[0]
      const course = snapshot.data()
      console.log('course: ', course)
      return { course }
    }
    return {}
  },
  data () {
    return {
      course: {}
    }
  },
  mounted () {

  }
}
</script>
