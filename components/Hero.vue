<template>
  <div id="hero">
    <div class="hero__tile" v-for="(videoItem, index) in content" :key="index">
      <video
        class="explore-cards__video"
        :poster="`${videoItem.videoThumbnail}`"
        loop
        muted
      >
        <source :src="`${videoItem.video}`" type="video/mp4" />
      </video>
    </div>
    <!-- <div class="hero__tile">
      <img
        src="https://images.unsplash.com/photo-1598300042247-d088f8ab3a91?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8OXx8cmFuZG9tJTIwb2JqZWN0c3xlbnwwfHwwfHw%3D&auto=format&fit=crop&w=800&q=70"
      />
    </div> -->
  </div>
</template>

<script>
// importing Thumnails
import weirdWaterThumbnail from '~/assets/videoThumbnails/weird-water.jpg';

// importing videos
import weirdWater from '~/assets/videos/weird-water.mp4';

export default {
  name: 'Hero',
  data() {
    return {
      content: [
        {
          videoThumbnail: weirdWaterThumbnail,
          video: weirdWater,
        },
        {
          videoThumbnail: weirdWaterThumbnail,
          video: weirdWater,
        },
        {
          videoThumbnail: weirdWaterThumbnail,
          video: weirdWater,
        },
        {
          videoThumbnail: weirdWaterThumbnail,
          video: weirdWater,
        },
        {
          videoThumbnail: weirdWaterThumbnail,
          video: weirdWater,
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
  height: 140vmax;
  width: 140vmax;
  //   width: 120vw;
  //   height: 180vh;
  padding-bottom: 5em;
  position: relative;
}

.hero__tile {
  position: absolute;
  transition: transform 800ms ease;
}

.hero__tile:hover {
  transform: scale(1.1);
}

// .hero__tile:hover > img {
//   opacity: 1;
//   transform: scale(1.01);
// }

// video
.hero__tile:hover > video {
  position: relative;
  opacity: 1;
  z-index: 9;
  transform: scale(1.01);
  //   width: 100%;
  //   height: auto;
  //   border: 2px solid red;
}

// .hero__tile > img {
//   height: 100%;
//   width: 100%;
//   object-fit: cover;
//   border-radius: inherit;
//   opacity: 0;
//   transition: opacity 800ms ease, transform 800ms ease;
// }

// video
.hero__tile > video {
  position: relative;
  z-index: -1;
  height: auto;
  width: 35em;
  //   object-fit: cover;
  border-radius: inherit;
  opacity: 0.5;
  transition: opacity 800ms ease, transform 800ms ease;
}

.hero__tile:nth-child(1) {
  //   height: 14%;
  //   width: 20%;
  left: 50%;
  top: 20%;
}

.hero__tile:nth-child(2) {
  //   height: 24%;
  //   width: 14%;
  left: 30%;
  top: 30%;
}

.hero__tile:nth-child(3) {
  //   height: 18%;
  //   width: 16%;
  left: 15%;
  top: 40%;
}

.hero__tile:nth-child(4) {
  //   height: 14%;
  //   width: 12%;
  left: 26%;
  top: 50%;
  video {
    height: auto;
    width: 40em;
  }
}

.hero__tile:nth-child(5) {
  //   height: 16%;
  //   width: 32%;
  left: 45%;
  top: 60%;

  video {
    height: auto;
    width: 40em;
  }
}

.hero__tile:nth-child(6) {
  //   height: 24%;
  //   width: 24%;
  left: 68%;
  top: 8%;
}

.hero__tile:nth-child(7) {
  //   height: 16%;
  //   width: 20%;
  left: 50%;
  top: 74%;
}

.hero__tile:nth-child(8) {
  //   height: 24%;
  //   width: 18%;
  left: 72%;
  top: 42%;
}

.hero__tile:nth-child(9) {
  //   height: 10%;
  //   width: 8%;
  left: 84%;
  top: 84%;
}

@media screen and (max-width: 1098px) {
  // video
  .hero__tile > video {
    width: 25em;
  }

  .hero__tile:nth-child(4) {
    video {
      height: auto;
      width: 30em;
    }
  }

  .hero__tile:nth-child(5) {
    video {
      height: auto;
      width: 30em;
    }
  }
}
@media screen and (max-width: 839px) {
  // video
  .hero__tile > video {
    width: 20em;
  }

  .hero__tile:nth-child(4) {
    video {
      height: auto;
      width: 24em;
    }
  }

  .hero__tile:nth-child(5) {
    video {
      height: auto;
      width: 24em;
    }
  }
}
@media screen and (max-width: 639px) {
  // video
  .hero__tile > video {
    width: 15em;
  }

  .hero__tile:nth-child(4) {
    video {
      height: auto;
      width: 19em;
    }
  }

  .hero__tile:nth-child(5) {
    video {
      height: auto;
      width: 19em;
    }
  }
}
</style>
