<template>
  <header class="header">
    <div class="header__logo">
      <NuxtLink to="/"
        ><img src="../assets/logos/logo.jpg" alt="logo" />
      </NuxtLink>
    </div>
    <nav>
      <NuxtLink to="/about"> About Us </NuxtLink>
      <NuxtLink to="/contact"> Contact </NuxtLink>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'Header',
};
</script>
<style lang="scss" scoped>
.header {
  position: relative;
  top: 0;
  z-index: 99;
  width: 100%;
  padding: 1em 1em;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-family: 'Martel Sans', sans-serif;

  &__logo {
    a {
      text-decoration: none;
      img {
        width: 8em;
        height: auto;
        border-radius: 0.2em;
      }
    }
  }

  nav {
    a {
      text-decoration: none;
      color: #7d7d7d;
      font-size: 1.3em;
      font-weight: 300;
      transition: 0.5s;
    }

    a:hover {
      color: #ffffff;
    }
    a:not(:last-child) {
      margin-right: 1em;
    }
  }
}
</style>
