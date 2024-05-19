<template>
  <div class="container">
    <a href="/" class="logo">
      <img src="~/assets/images/logo.png" alt="logo" />
    </a>
    <div class="video-list">
      <Video
        src="https://file.notion.so/f/f/170ef98a-54c7-420e-9e67-c7e5378944ff/adffa2e3-aee8-4fc8-b4be-a3986cbcb5b5/%E1%84%82%E1%85%AC.mp4?id=de9ce384-28fa-44d4-9ef2-d7a9141a190e&table=block&spaceId=170ef98a-54c7-420e-9e67-c7e5378944ff&expirationTimestamp=1716199200000&signature=3DHEt13mzApblDFVCzZb8Te0t-nC24_qQFrbQTulYZA&downloadName=%E1%84%82%E1%85%AC.mp4"
        thumbnail="https://file.notion.so/f/f/170ef98a-54c7-420e-9e67-c7e5378944ff/56dbf488-ecf0-4791-9746-a99398772558/main1.png?id=3ea6af1c-0335-47d4-a551-1b171c5b156b&table=block&spaceId=170ef98a-54c7-420e-9e67-c7e5378944ff&expirationTimestamp=1716199200000&signature=rqswRARMlGc1UQSuYlr3vMBV6y_tBZUX2cEWk_xbZP8&downloadName=main1.png"
        class="wide"
        ref="video"
      />
      <Video
        src="https://file.notion.so/f/f/170ef98a-54c7-420e-9e67-c7e5378944ff/0378847d-e662-4b31-9de7-6285ec290782/DB.mp4?id=cfb46702-37ed-4360-82be-53ee65569835&table=block&spaceId=170ef98a-54c7-420e-9e67-c7e5378944ff&expirationTimestamp=1716199200000&signature=mla82KUVO5hegrw9uVJGB4Yuw88BQk-q0CmQ2hC6FMc&downloadName=DB.mp4"
        thumbnail="https://file.notion.so/f/f/170ef98a-54c7-420e-9e67-c7e5378944ff/740294a1-2d63-4ef3-89d9-0a12ed2d5244/main2.png?id=fd3a6846-6129-4acb-9104-5e20477189c4&table=block&spaceId=170ef98a-54c7-420e-9e67-c7e5378944ff&expirationTimestamp=1716199200000&signature=RmKXDsiP2X3P4H4_n9bhe3ATWay5_aF5MqJmfz5lgsY&downloadName=main2.png"
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
