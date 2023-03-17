<template>
  <header class="header">
    <div class="header__logo">
      <NuxtLink to="/"
        ><img data-aos="zoom-in" src="../assets/logos/logo.png" alt="logo" />
      </NuxtLink>
    </div>

    <nav class="header__navigation-links">
      <div class="header__hamburger-icon" @click="showHideNavbar">
        <span id="header__hamburger-top-line"></span>
        <span id="header__hamburger-middle-line"></span>
        <span id="header__hamburger-bottom-line"></span>
      </div>
      <div class="header__links" id="header__nav-links">
        <NuxtLink
          to="/"
          :class="homePage ? 'header__active-link' : 'header__link'"
        >
          HOME
        </NuxtLink>

        <NuxtLink
          to="/contact"
          :class="contactPage ? 'header__active-link' : 'header__link'"
        >
          CONTACT
        </NuxtLink>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      isHomePage: false,
      isContactPage: false,
    };
  },
  computed: {
    homePage() {
      return this.isHomePage;
    },
    contactPage() {
      return this.isContactPage;
    },
  },
  watch: {
    $route() {
      this.isHomePage = window.location.pathname === '/';
      this.isContactPage = window.location.pathname === '/contact';
    },
  },
  mounted() {
    this.isHomePage = window.location.pathname === '/';
    this.isContactPage = window.location.pathname === '/contact';
  },
  methods: {
    showHideNavbar() {
      const navLinksDisplay = document.getElementById('header__nav-links');
      const iconMiddleLine = document.getElementById(
        'header__hamburger-middle-line',
      );
      const iconTopLine = document.getElementById('header__hamburger-top-line');
      const iconBottomLine = document.getElementById(
        'header__hamburger-bottom-line',
      );
      if (navLinksDisplay.style.display === 'flex') {
        navLinksDisplay.style.display = 'none';
        iconMiddleLine.style.display = 'inline-block';
        iconTopLine.classList.remove('header__icon-line-animate');
        iconBottomLine.classList.remove('header__icon-bottom-line-animate');
        navLinksDisplay.classList.remove('header__link-animate');
      } else {
        navLinksDisplay.style.display = 'flex';
        iconMiddleLine.style.display = 'none';
        iconTopLine.classList.add('header__icon-line-animate');
        iconBottomLine.classList.add('header__icon-bottom-line-animate');
        navLinksDisplay.classList.add('header__link-animate');
      }
    },
  },
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
  font-family: 'Rubik Mono One', sans-serif;

  &__logo {
    position: relative;
    a {
      text-decoration: none;
      img {
        position: relative;
        z-index: -1;
        width: 7em;
        height: auto;
        border-radius: 0.2em;
      }
    }
  }

  &__link {
    color: #ffffff;
    text-decoration: none;
    font-size: 1.3em;
    font-weight: 300;
    transition: 0.5s;

    &:hover {
      color: rgb(141, 117, 50);
    }

    &:not(:last-child) {
      margin-right: 1em;
    }
  }

  // Active link stying
  &__active-link {
    font-size: 1.3em;
    font-weight: 300;
    transition: 0.5s;
    text-decoration: none;
    color: rgba(255, 185, 0, 1);

    &:not(:last-child) {
      margin-right: 1em;
    }
  }

  &__hamburger-icon {
    position: absolute;
    top: 1.5em;
    left: 1em;
    width: 1.65em;
    height: 1.2em;
    display: none;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    cursor: pointer;
    z-index: 9;

    span {
      position: relative;
      display: inline-block;
      width: 100%;
      height: 0.1em;
      border-radius: 0.05em;
      background: #ffffff;
    }
  }

  &__icon-line-animate {
    animation: rotateLine 0.5s linear forwards;
  }

  &__icon-bottom-line-animate {
    animation: rotateBottomLine 0.5s linear forwards;
  }

  @keyframes rotateLine {
    0% {
      transform: rotate(0deg);
      top: 50%;
      background: #ffffff;
    }
    100% {
      transform: rotate(45deg);
      top: 50%;
      background: #ffffff;
    }
  }

  @keyframes rotateBottomLine {
    0% {
      transform: rotate(0deg);
      bottom: 50%;
      background: #ffffff;
    }
    100% {
      transform: rotate(-45deg);
      bottom: 50%;
      background: #ffffff;
    }
  }

  @media screen and (max-width: 768px) {
    &__logo {
      left: 3em;
      a {
        img {
          width: 6em;
        }
      }
    }

    &__hamburger-icon {
      display: flex;
    }

    #header__nav-links {
      display: none;
    }

    &__link-animate {
      a {
        animation: slideRight 0.2s linear forwards;
      }

      a:nth-child(2) {
        animation: slideRightDelay 0.2s 0.1s ease-in-out 1 forwards;
      }
    }

    @keyframes slideRight {
      0% {
        margin-left: -50%;
      }
      100% {
        margin-left: 2em;
      }
    }

    @keyframes slideRightDelay {
      0% {
        margin-left: -50%;
      }
      100% {
        margin-left: 2.5em;
      }
    }

    // Active link stying
    &__active-link {
      margin-left: 0em;
      color: #252424;
      background: rgba(255, 185, 0, 1);
    }

    &__links {
      position: absolute;
      top: 0;
      left: 0;
      width: 45vw;
      height: 100vh;
      justify-content: center;
      min-width: 18em;
      margin-right: 0;
      padding: 7em 0 0 0;
      display: flex;
      justify-content: flex-start;
      align-items: flex-start;
      flex-direction: column;
      background: #252424;
      text-align: center;

      a {
        font-size: 1em;
        padding: 0.1em 0.3em 0.05em 0.3em;
      }

      a:not(:last-child) {
        margin-bottom: 1em;
      }
    }
  }
}
</style>
