<template>
  <Header />
  <div class="contact">
    <div class="contact__details">
      <h1>HI<span>,</span></h1>
      <h2>I'M A VIDEO EDITOR SPECIALIZED IN SHORT-FORM CONTENT.</h2>
      <h3>IF YOU'RE INTERESTED, YOU CAN CONTACT ME THROUGH MY TWITTER.</h3>
      <NuxtLink to="https://twitter.com/" target="_blank"> TWITTER </NuxtLink>
      <p>-DNIEL</p>
    </div>
  </div>
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
  font-family: 'Bebas Neue', cursive;
  font-size: 3em;
  height: 100vh;
  color: #ffffff;
  display: flex;
  justify-content: center;
  align-items: center;

  &__details {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-top: -3em;

    h1 {
      font-size: 1.5em;
      color: #ffb900;
      margin: 0;
      font-weight: 400;
      line-height: 1;
      span {
        color: #ffffff;
      }
    }

    h2 {
      font-size: 1em;
      width: 10em;
      font-weight: 400;
      line-height: 1;
      margin-top: 0.5em;
    }

    h3 {
      margin-top: 0.5em;
      font-size: 0.65em;
      width: 20em;
      font-weight: 400;
    }

    a {
      margin-top: 0.85em;
      background-color: rgba(236, 182, 33, 1);
      color: rgba(28, 28, 28, 1);
      font-family: 'Rubik Mono One', sans-serif;
      width: 100%;
      min-width: 18em;
      font-weight: 400;
      text-decoration: none;
      font-size: 0.35em;
      padding: 0.45em 0 0.25em 0;
      border-radius: 0.2em;
    }

    p {
      margin-top: 0.5em;
      text-transform: uppercase;
      color: #ffb900;
      font-size: 0.875em;
    }
  }
}
</style>
