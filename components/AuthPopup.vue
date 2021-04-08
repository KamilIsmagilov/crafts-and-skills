<template>
  <div>
    <t-modal :value="value" header="SignIn/SignUp">
      <div id="firebaseui-auth-container"></div>
    </t-modal>
  </div>
</template>

<script>
import firebase from 'firebase'
import 'firebaseui/dist/firebaseui.css'
import { TModal } from 'vue-tailwind/dist/components'

export default {
  name: 'AuthPopup',
  components: {
    TModal
  },
  props: {
    value: {
      type: Boolean,
      default: false
    }
  },
  computed: {
    isShow() {
      return this.isShowAuthModal
    }
  },
  mounted() {
    if (process.client) {
      // FirebaseUI config.
      const uiConfig = {
        signInSuccessUrl: '/',
        signInOptions: [
          // Leave the lines as is for the providers you want to offer your users.
          firebase.auth.GoogleAuthProvider.PROVIDER_ID,
          firebase.auth.FacebookAuthProvider.PROVIDER_ID,
          firebase.auth.TwitterAuthProvider.PROVIDER_ID,
          firebase.auth.GithubAuthProvider.PROVIDER_ID,
          firebase.auth.EmailAuthProvider.PROVIDER_ID
          // firebase.auth.PhoneAuthProvider.PROVIDER_ID,
          // firebaseui.auth.AnonymousAuthProvider.PROVIDER_ID
        ],
        // tosUrl and privacyPolicyUrl accept either url string or a callback
        // function.
        // Terms of service url/callback.
        tosUrl: '<your-tos-url>'
        // Privacy policy url/callback.
        // privacyPolicyUrl: function() {
        //   window.location.assign('<your-privacy-policy-url>')
        // }
      }

      // Initialize the FirebaseUI Widget using Firebase.
      const ui = new window.firebaseui.auth.AuthUI(firebase.auth())
      // The start method will wait until the DOM is loaded.
      ui.start('#firebaseui-auth-container', uiConfig)
    }
  }
}
</script>
