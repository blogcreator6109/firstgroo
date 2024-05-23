<template>
  <div class="container">
    <a href="/" class="logo">
      <img src="~/assets/images/logo.png" alt="logo" />
    </a>
    <div class="video-list">
      <Video
        src="neurovideo.mp4"
        thumbnail="neuroThumb.png"
        class="wide"
        ref="video"
      />
      <Video
        src="DBvideo.mp4"
        thumbnail="dbThumb.png"
        class="wide"
        ref="video"
      />
      <Youtube value="Zj-yQJa4Qo4" ref="video" />
      <Youtube value="dgsPOQv--HI" ref="video" />
      <Youtube value="0P_VQmfvH_4" ref="video" />
      <Youtube value="iaCvDy15zRs" ref="video" />
      <Youtube value="NHh3udthVDI" ref="video" />
    </div>
  </div>
</template>

<style lang="scss">
@import "animate.css";
body {
  margin: 0;
  padding: 0;
}
.container {
  max-width: 100%;
  width: 900px;
  display: flex;
  flex-direction: column;
  align-items: center;

  margin: 0px auto;
  padding: 100px 0;
  box-sizing: border-box;

  .logo {
    margin-bottom: 50px;
    img {
      width: 250px;
      border-radius: 10px;
    }
  }

  .video-list {
    width: 100%;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 30px;

    .wide {
      grid-column: span 2;
    }

    .video,
    .youtube {
      opacity: 0;
      transition: all 0.7s ease;
      pointer-events: none;

      &:nth-of-type(2n- 1) {
        transform: translateX(-200px);
      }
      &:nth-of-type(2n) {
        transform: translateX(200px);
      }

      &.active {
        pointer-events: initial;
        opacity: 1;
        transform: translateX(0);
      }
    }
  }
}

@media (max-width: 768px) {
  .container {
    padding: 50px 10px;
    width: 100%;

    .logo {
      margin-bottom: 30px;
      img {
        width: 150px;
      }
    }

    .video-list {
      grid-template-columns: 1fr;

      .wide {
        grid-column: span 1;
      }
    }
  }
}
</style>
