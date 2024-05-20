<template>
  <div class="container">
    <a href="/" class="logo">
      <img src="~/assets/images/logo.png" alt="logo" />
    </a>
    <div class="video-list">
      <Video
        src="neurovideo.mp4"
        thumbnail="https://file.notion.so/f/f/170ef98a-54c7-420e-9e67-c7e5378944ff/7b95fb8c-29e0-4cef-91c4-9d32212e36ac/%E1%84%82%E1%85%B2%E1%84%85%E1%85%A9%E1%84%91%E1%85%B5%E1%86%BA_%E1%84%8A%E1%85%A5%E1%86%B7%E1%84%82%E1%85%A6%E1%84%8B%E1%85%B5%E1%86%AF.png?id=6d87eb74-baf8-4942-9bb1-4dc9998af65f&table=block&spaceId=170ef98a-54c7-420e-9e67-c7e5378944ff&expirationTimestamp=1716242400000&signature=ShcXJ11e9o0HwTua0gQZj742MFYY1_zrMgTIK8Z2C78&downloadName=%E1%84%82%E1%85%B2%E1%84%85%E1%85%A9%E1%84%91%E1%85%B5%E1%86%BA_%E1%84%8A%E1%85%A5%E1%86%B7%E1%84%82%E1%85%A6%E1%84%8B%E1%85%B5%E1%86%AF.png"
        class="wide"
        ref="video"
      />
      <Video
        src="DBvideo.mp4"
        thumbnail="https://file.notion.so/f/f/170ef98a-54c7-420e-9e67-c7e5378944ff/fab348b2-9531-4e12-b8f7-66ab3042d678/DB_%E1%84%8A%E1%85%A5%E1%86%B7%E1%84%82%E1%85%A6%E1%84%8B%E1%85%B5%E1%86%AF.png?id=6baa3b3e-7f0e-441e-9f53-b535f006efd7&table=block&spaceId=170ef98a-54c7-420e-9e67-c7e5378944ff&expirationTimestamp=1716242400000&signature=zeUcqko2ONVcXvnrcf5hq3MObtf477v3posurke9Bms&downloadName=DB_%E1%84%8A%E1%85%A5%E1%86%B7%E1%84%82%E1%85%A6%E1%84%8B%E1%85%B5%E1%86%AF.png"
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
