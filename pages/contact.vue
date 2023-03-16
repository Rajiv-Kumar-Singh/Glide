<template>
  <Header />
  <div class="contact">This is Contact page</div>
</template>

<script>
import Header from '~/components/Header';
export default {
  name: 'Contact',
  components: {
    Header,
  },
};
</script>
<style lang="scss" scoped>
.contact {
  position: relative;
  top: 0;
  text-align: center;
  color: #ffffff;
}
</style>
