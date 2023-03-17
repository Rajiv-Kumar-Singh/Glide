<template>
  <div>
    <Header />
    <NuxtPage />
  </div>
</template>
<script>
import Header from '~/components/Header';
// import animate-on-scroll library for adding scroll animation
import AOS from 'aos';
import 'aos/dist/aos.css';

export default {
  name: 'App',
  components: {
    Header,
  },

  mounted() {
    // Scroll Animation settings
    AOS.init({
      duration: 800,
      delay: 0,
      once: true,
      easing: 'ease-in-out',
    });
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background-color: #000000;
  overflow: hidden;
}
</style>

