<template>
  <div class="hero" id="hero">
    <!-- First column content -->
    <div
      class="hero__tile"
      v-for="(videoItem, index) in firstColumnContent"
      :key="index"
    >
      <video
        class="explore-cards__video"
        data-aos="flip-left"
        :data-aos-delay="`${videoItem.animationDelay}`"
        data-aos-offset="-1000"
        :poster="`${videoItem.videoThumbnail}`"
        loop
        muted
      >
        <source :src="`${videoItem.video}`" type="video/mp4" />
      </video>
    </div>
    <!-- Logo   -->
    <div class="hero__tile" data-aos="zoom-in">
      <img src="../assets/gifs/brand.gif" loading="lazy" />
    </div>
    <!-- Second column content -->
    <div
      class="hero__tile"
      v-for="(videoItem, index) in secondColumnContent"
      :key="index"
    >
      <video
        class="explore-cards__video"
        data-aos="flip-right"
        data-aos-offset="-1000"
        :data-aos-delay="`${videoItem.animationDelay}`"
        :poster="`${videoItem.videoThumbnail}`"
        loop
        muted
      >
        <source :src="`${videoItem.video}`" type="video/mp4" />
      </video>
    </div>
  </div>
</template>

<script>
// importing Thumnails
import thumbnail from '~/assets/videoThumbnails/thumbnail.jpg';

// importing videos
import weirdWater from '~/assets/videos/demo-video.mp4';

export default {
  name: 'Hero',
  data() {
    return {
      firstColumnContent: [
        {
          videoThumbnail: thumbnail,
          video: weirdWater,
          animationDelay: 100,
        },
        {
          videoThumbnail: thumbnail,
          video: weirdWater,
          animationDelay: 200,
        },
        {
          videoThumbnail: thumbnail,
          video: weirdWater,
          animationDelay: 300,
        },
      ],
      secondColumnContent: [
        {
          videoThumbnail: thumbnail,
          video: weirdWater,
          animationDelay: 100,
        },
        {
          videoThumbnail: thumbnail,
          video: weirdWater,
          animationDelay: 200,
        },
        {
          videoThumbnail: thumbnail,
          video: weirdWater,
          animationDelay: 300,
        },
      ],
    };
  },
  mounted() {
    const hero = document.getElementById('hero');

    window.onmousemove = (e) => {
      const mouseX = e.clientX,
        mouseY = e.clientY;

      const xDecimal = mouseX / window.innerWidth,
        yDecimal = mouseY / window.innerHeight;

      const maxX = hero.offsetWidth - window.innerWidth,
        maxY = hero.offsetHeight - window.innerHeight;

      const panX = maxX * xDecimal * -1,
        panY = maxY * yDecimal * -1;

      hero.animate(
        {
          transform: `translate(${panX}px, ${panY}px)`,
        },
        {
          duration: 4000,
          fill: 'forwards',
          easing: 'ease',
        },
      );
    };

    // play video upon HOVER
    const video = document.getElementsByClassName('explore-cards__video');
    let i;
    for (i = 0; i < video.length; i++) {
      video[i].addEventListener('mouseover', function () {
        this.play();
      });
      video[i].addEventListener('mouseout', function () {
        this.pause();
      });
    }
  },
};
</script>

<style lang="scss" scoped>
#hero {
  height: 60vmax;
  width: 95vmax;
  padding-bottom: 5em;
  position: relative;
  top: 0;
  color: #ffffff;

  @media screen and (max-width: 1190px) {
    & {
      height: 75vmax;
    }
  }
  @media screen and (max-width: 1044px) {
    & {
      height: 80vmax;
    }
  }
  @media screen and (max-width: 988px) {
    & {
      height: 85vmax;
    }
  }

  @media screen and (max-width: 786px) {
    & {
      height: 120vmax;
    }
  }

  @media screen and (max-width: 703px) {
    & {
      height: 110vmax;
    }
  }
  @media screen and (max-width: 638px) {
    & {
      width: 90vmax;
    }
  }
  @media screen and (max-width: 568px) {
    & {
      width: 90vmax;
      height: 100vmax;
    }
  }
}

.hero {
  &__tile {
    position: absolute;
    transition: transform 800ms ease;
  }

  &__tile > video {
    position: relative;
    z-index: -1;
    height: auto;
    width: 8em;
    object-fit: cover;
    border-radius: inherit;
    opacity: 0.5;
    transition: opacity 800ms ease, transform 800ms ease;
  }

  &__tile:hover > video {
    opacity: 1;
    z-index: 9;
    transform: scale(1.5);
  }

  &__tile:hover {
    z-index: 9;
  }

  &__tile:nth-child(1) {
    left: 22%;
    top: 5%;
    animation: motion 10s linear infinite;
  }

  &__tile:nth-child(2) {
    left: 15%;
    top: 27.5%;
    animation: motion 8s linear infinite;
  }

  &__tile:nth-child(3) {
    left: 22%;
    top: 50%;
    animation: motion 6s linear infinite;
  }

  &__tile:nth-child(4) {
    left: 35%;
    top: 26%;

    img {
      position: relative;
      z-index: -2;
      height: auto;
      width: 25em;
      object-fit: cover;
      border-radius: inherit;
    }
  }

  &__tile:nth-child(5) {
    left: 67%;
    top: 5%;
    animation: motion 6s linear infinite;
  }

  &__tile:nth-child(6) {
    left: 74%;
    top: 27.5%;
    animation: motion 8s linear infinite;
  }

  &__tile:nth-child(7) {
    left: 67%;
    top: 50%;
    animation: motion 6s linear infinite;
  }

  @media screen and (max-width: 1190px) {
    &__tile {
      &:nth-child(2) {
        left: 15%;
        top: 25.5%;
      }

      &:nth-child(3) {
        left: 22%;
        top: 45.5%;
      }

      &:nth-child(4) {
        left: 33.5%;
        img {
          width: 23em;
        }
      }

      &:nth-child(5) {
        left: 67%;
      }

      &:nth-child(6) {
        left: 74%;
        top: 25.5%;
      }

      &:nth-child(7) {
        left: 67%;
        top: 45.5%;
      }
    }
  }

  @media screen and (max-width: 1044px) {
    &__tile {
      &:hover > video {
        transform: scale(1.3);
      }

      &:nth-child(1) {
        left: 18%;
        top: 5%;
      }

      &:nth-child(2) {
        left: 12%;
        top: 30%;
      }

      &:nth-child(3) {
        left: 18%;
        top: 55%;
      }

      &:nth-child(4) {
        left: 30%;
      }

      &:nth-child(6) {
        top: 30%;
      }

      &:nth-child(7) {
        top: 55%;
      }
    }
  }

  @media screen and (max-width: 988px) {
    &__tile {
      &:nth-child(2) {
        left: 12%;
        top: 25%;
      }

      &:nth-child(3) {
        top: 45%;
      }

      &:nth-child(6) {
        top: 25%;
      }

      &:nth-child(7) {
        top: 45%;
      }
    }
  }

  @media screen and (max-width: 944px) {
    &__tile {
      & > video {
        width: 8em;
      }

      &:nth-child(1) {
        left: 10%;
      }

      &:nth-child(2) {
        left: 2%;
        top: 30%;
      }

      &:nth-child(3) {
        left: 10%;
        top: 55%;
      }

      &:nth-child(4) {
        img {
          width: 20em;
        }
      }

      &:nth-child(5) {
        left: 72%;
      }

      &:nth-child(6) {
        left: 80%;
        top: 30%;
      }

      &:nth-child(7) {
        left: 72%;
        top: 55%;
      }
    }
  }

  @media screen and (max-width: 786px) {
    &__tile {
      &:hover > video {
        transform: scale(1.2);
      }

      &:nth-child(1) {
        left: 10%;
      }

      &:nth-child(2) {
        top: 26%;
      }

      &:nth-child(3) {
        top: 48%;
      }

      &:nth-child(4) {
        img {
          width: 18em;
        }
      }

      &:nth-child(6) {
        left: 78%;
        top: 26%;
      }

      &:nth-child(7) {
        left: 72%;
        top: 48%;
      }
    }
  }

  @media screen and (max-width: 703px) {
    &__tile {
      & > video {
        width: 6em;
      }

      &:nth-child(1) {
        top: 10%;
      }

      &:nth-child(2) {
        top: 30%;
      }

      &:nth-child(3) {
        top: 50%;
      }

      &:nth-child(4) {
        left: 27%;
      }

      &:nth-child(5) {
        top: 10%;
      }

      &:nth-child(6) {
        top: 30%;
      }

      &:nth-child(7) {
        top: 50%;
      }
    }
  }
  @media screen and (max-width: 568px) {
    &__tile {
      & > video {
        width: 6em;
      }

      &:nth-child(1) {
        top: 10%;
      }

      &:nth-child(2) {
        top: 30%;
      }

      &:nth-child(3) {
        top: 50%;
      }

      &:nth-child(4) {
        left: 30%;
        top: 30%;
        img {
          width: 13em;
        }
      }

      &:nth-child(5) {
        top: 10%;
      }

      &:nth-child(6) {
        top: 30%;
      }

      &:nth-child(7) {
        top: 50%;
      }
    }
  }
}

@keyframes motion {
  0% {
    transform: translate3d(0px, 0px, 0px);
  }
  15% {
    transform: translate3d(5px, 2px, 0px);
  }
  30% {
    transform: translate3d(10px, 6px, 0px);
  }
  45% {
    transform: translate3d(15px, 10px, 0px);
  }
  60% {
    transform: translate3d(10px, 6px, 0px);
  }
  80% {
    transform: translate3d(5px, 2px, 0px);
  }
  100% {
    transform: translate3d(0px, 0px, 0px);
  }
}
</style>
