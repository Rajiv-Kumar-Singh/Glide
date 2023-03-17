<template>
  <div class="contact">
    <div class="contact__details">
      <h1 data-aos="fade-up">HI<span>,</span></h1>
      <h2 data-aos="fade-up" data-aos-delay="100">
        I'M A VIDEO EDITOR SPECIALIZED IN SHORT-FORM CONTENT.
      </h2>
      <h3 data-aos="fade-up" data-aos-delay="200">
        IF YOU'RE INTERESTED, YOU CAN CONTACT ME THROUGH MY TWITTER.
      </h3>
      <NuxtLink
        to="https://twitter.com/"
        target="_blank"
        data-aos="fade-up"
        data-aos-delay="300"
      >
        TWITTER
      </NuxtLink>
      <p data-aos="fade-up" data-aos-delay="400">-DNIEL</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Contact',
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
  padding: 0.5em;

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
      max-width: 10em;
      font-weight: 400;
      line-height: 1;
      margin-top: 0.5em;
    }

    h3 {
      margin-top: 0.5em;
      font-size: 0.65em;
      max-width: 20em;
      font-weight: 400;
      letter-spacing: 0.021em;
    }

    a {
      margin-top: 0.85em;
      background-color: rgba(236, 182, 33, 1);
      color: rgba(28, 28, 28, 1);
      font-family: 'Rubik Mono One', sans-serif;
      width: 100%;
      max-width: 50em;
      font-weight: 400;
      text-decoration: none;
      font-size: 0.35em;
      padding: 0.455em 0 0.255em 0;
      border-radius: 0.2em;
    }

    p {
      margin-top: 0.7em;
      text-transform: uppercase;
      color: #ffb900;
      font-size: 0.875em;
    }
  }

  @media screen and (max-width: 768px) {
    &__details {
      h1 {
        font-size: 1em;
      }
      h2 {
        font-size: 0.75em;
      }
      h3 {
        font-size: 0.5em;
      }
      a {
        font-size: 0.3em;
      }
      p {
        font-size: 0.8em;
      }
    }
  }
}
</style>
