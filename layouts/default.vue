<template>
  <div>
    <!-- <link rel="preconnect" href="https://fonts.gstatic.com">
    <link href="https://fonts.googleapis.com/css2?family=Lora:wght@500;600;700&family=Montserrat&display=swap" rel="stylesheet"> -->
    <div class="bg-gray-300 w-full h-16">
      <div class="text-base" @click="openAuthModal">SignIn/SignUp</div>
    </div>
    <AuthPopup :value="isShowAuthModal" />
    <Nuxt />
  </div>
</template>

<script>
import AuthPopup from '~/components/AuthPopup'

export default {
  components: {
    AuthPopup
  },
  data () {
    return {
      isShowAuthModal: false
    }
  },
  methods: {
    openAuthModal () {
      this.isShowAuthModal = true
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Lora:wght@500;600;700&family=Montserrat&display=swap');
</style>

<style>
html {
  font-family: 'Montserrat', sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

/* font-family: 'Lora', serif;
 */

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>
