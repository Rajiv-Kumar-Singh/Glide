<template>
  <Header />
  <div class="about">This is About page</div>
</template>

<script>
import Header from '~/components/Header';
export default {
  name: 'About',
  components: {
    Header,
  },
};
</script>
<style lang="scss" scoped>
.about {
  position: relative;
  top: 0;
  text-align: center;
  color: #ffffff;
}
</style>
