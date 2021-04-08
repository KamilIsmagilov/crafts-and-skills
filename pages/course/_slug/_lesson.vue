<template>
  <div>
    {{ this.lesson }}
    <Test :questions="test" />
  </div>
</template>

<script>
import firebase from 'firebase'
const db = firebase.firestore()

import Test from '~/components/Test'

export default {
  async asyncData ({ params }) {
    console.log('params: ', params)
    const slug = params.slug
    const lessonSlug = params.lesson
    const query = await db.collection('courses')
      .where('slug', '==', slug)
      .limit(1)
      .get()
    if (!query.empty) {
      const snapshot = query.docs[0]
      const course = snapshot.data()
      const lesson = course.lessons.find(item => item.lessonSlug === lessonSlug)
      return { lesson }
    }
    return {}
  },
  components: {
    Test
  },
  data () {
    return {
      test: [
        {
          question: 'Which of the benefits does NOT apply to frameworks?',
          answers: [
            {
              text: '"Standardized" project structure, familiar to fans of a particular framework'
            },
            {
              text: 'Component approach (componentize)'
            },
            {
              text: 'No need to write JS code yourself',
              is_right: true
            },
            {
              text: 'Useful framework toolkit'
            }
          ]
        },
        {
          question: 'With vue-cli we can quickly create a minimal vue application and then deploy it',
          answers: [
            {
              text: 'Yes',
              is_right: true
            },
            {
              text: 'No'
            }
          ]
        },
        {
          question: '',
          answers: [
            '',
            '',
            '',
            ''
          ]
        },
        {
          question: '',
          answers: [
            '',
            '',
            '',
            ''
          ]
        }
      ]
    }
  }
}
</script>
