<template>
  <ScrolledSection>
    <template #container>
      <div class="wrapper">
        <div class="container">
          <div class="txt1">
            <img src="@/assets/images/banner/txt1.svg" alt="說明文字" />
          </div>
          <div class="logo">
            <div>
              <img src="@/assets/images/banner/img1.png" alt="" />
            </div>
            <div>
              <img src="@/assets/images/banner/logo.svg" alt="" />
            </div>
            <div>
              <img src="@/assets/images/banner/img2.png" alt="" />
            </div>
          </div>
          <div class="txt2">
            <img src="@/assets/images/banner/txt2.svg" alt="說明文字" />
          </div>
          <div class="txt3">
            <img src="@/assets/images/banner/txt3.svg" alt="說明文字" />
          </div>
          <div class="decoration">
            <div>
              <img src="@/assets/images/banner/img3.png" alt="" />
            </div>
            <div>
              <img src="@/assets/images/banner/img4.png" alt="" />
            </div>
          </div>
        </div>
      </div>
    </template>
  </ScrolledSection>
</template>

<script setup lang="ts">
import ScrolledSection from "@/components/ScrolledSection.vue";
</script>

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
        }

        &:last-child {
          width: 25%;
        }

        &:nth-child(2) {
          width: 35%;

          @include desktops {
            width: 20%;
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
    }
    .txt3 {
      width: 65%;
      margin: 0 auto 10%;

      @include desktops {
        margin-bottom: 0;
        width: 36%;
      }
    }

    .decoration {
      display: flex;
      align-items: flex-end;

      div {
        &:first-child {
          width: 15%;
        }
        &:last-child {
          width: 85%;
        }

        img {
          width: 100%;
        }
      }
    }
  }
}
</style>
