<template>
  <section class="wrapper">
    <div class="container">
      <div class="txt1">
        <img class="fadeInElement" src="@/assets/images/banner/txt1.svg" alt="說明文字" />
      </div>
      <div class="logo">
        <div>
          <img class="fadeInElement" src="@/assets/images/banner/img1.png" alt="" />
        </div>
        <div>
          <img class="fadeInElement" src="@/assets/images/banner/logo.svg" alt="" />
        </div>
        <div>
          <img class="fadeInElement" src="@/assets/images/banner/img2.png" alt="" />
        </div>
      </div>
      <div class="txt2">
        <img class="fadeInElement" src="@/assets/images/banner/txt2.svg" alt="說明文字" />
      </div>
      <div class="txt3">
        <img class="fadeInElement" src="@/assets/images/banner/txt3.svg" alt="說明文字" />
      </div>
      <div class="decoration">
        <div>
          <img class="fadeInElement" src="@/assets/images/banner/img3.png" alt="" />
        </div>
        <div>
          <img class="fadeInElement" src="@/assets/images/banner/img4.png" alt="" />
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.wrapper {
  margin-bottom: 62px;
  width: 100%;
  height: calc(100vh - 60px - 2px);
  background-image: url("@/assets/images/banner/bg.jpg");
  display: flex;
  justify-content: center;
  align-items: center;

  @include desktops {
    height: 100vh;
  }

  .container {
    width: 90%;

    @include pad {
      width: 60%;
    }

    .txt1 {
      width: 80%;
      margin: 0 auto 5%;

      @include pad {
        margin-bottom: 4%;
      }

      @include desktops {
        width: 40%;
      }

      img {
        width: 100%;
      }

      img.show {
        @include fadeAndMoveUpAnimation()
      }
    }

    .logo {
      margin-bottom: 10%;
      width: 100%;
      display: flex;
      justify-content: center;
      align-items: flex-end;
      gap: 5%;

      @include desktops {
        margin-bottom: 5%;
      }

      div {
        &:first-child {
          width: 25%;

          .fadeInElement.show {
            @include fadeAndMoveRightAnimation(.2s)
          }
        }

        &:last-child {
          width: 25%;

          .fadeInElement.show {
            @include fadeAndMoveLeftAnimation(.2s)
          }
        }

        &:nth-child(2) {
          width: 35%;

          @include desktops {
            width: 20%;
          }

          .fadeInElement.show {
            @include fadeAndMoveUpAnimation(.2s)
          }
        }
      }

      img {
        width: 100%;
      }
    }

    .txt2 {
      width: 75%;
      margin: 0 auto 2%;

      @include desktops {
        margin-bottom: 1%;
        width: 44%;
      }

      .fadeInElement.show {
        @include fadeAndMoveUpAnimation(.4s)
      }
    }

    .txt3 {
      width: 65%;
      margin: 0 auto 10%;

      @include desktops {
        margin-bottom: 0;
        width: 36%;
      }

      .fadeInElement.show {
        @include fadeAndMoveUpAnimation(.5s)
      }
    }

    .decoration {
      display: flex;
      align-items: flex-end;

      div {
        &:first-child {
          width: 15%;

          .fadeInElement.show {
            @include fadeAndMoveRightAnimation(.8s)
          }
        }

        &:last-child {
          width: 85%;

          .fadeInElement.show {
            @include fadeAndMoveLeftAnimation(.8s)
          }
        }

        img {
          width: 100%;
        }
      }
    }
  }
}
</style>
