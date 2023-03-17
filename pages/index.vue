<template>
  <Header />
  <Hero />
</template>

<script>
import Header from '~/components/Header';
import Hero from '~/components/Hero';

export default {
  name: 'HomePage',
  components: {
    Header,
    Hero,
  },
};
</script>
