<template>
  <section>
    <div class="title">
      <h2 class="fadeInElement">Heart of Taipei</h2>
      <h2 class="fadeInElement">城市中軸 無可限量</h2>
    </div>
    <div class="text">
      <p class="fadeInElement">126坪寸寸精華 定錨資產座標</p>
      <p class="fadeInElement">
        中山門戶—中山北大道與⺠生東路交織，傳奇地段，金脈商冑雲集，松山機場、雙子星權掌雙國門樞紐。「交通、政經、商業、時尚、藝文、公園」強強交匯，無法複製的地段，成就永恆價值，多年等候一見鍾情。
      </p>
    </div>
    <div class="pic" @touchstart="touch">
      <img src="@/assets/images/location/s2.jpg" alt="" />
    </div>
    <p v-if="showHint">
      <span>可左右滑動</span>
    <div>
      <span>&larr;</span>
      <span>&rarr;</span>
    </div>
    </p>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const showHint = ref(true)
const touch = () => {
  if (showHint.value)
    showHint.value = false
}
</script>

<style lang="scss" scoped>
section {
  margin-bottom: 48px;
  width: 100%;
  position: relative;
  font-family: "Noto Sans TC", sans-serif;
  letter-spacing: 2px;

  .title,
  .text {
    padding: 0 15px;

    @include desktops {
      width: 30%;
      position: absolute;
      top: 10%;
    }


  }

  .title {
    font-size: 18px;

    @include desktops {
      left: 10%;
    }

    h2 {

      @include desktops {
        color: #fff;
      }

      &:first-child {
        @include desktops {
          font-size: 14px;
        }

        @include smallScreen {
          font-size: 20px;

        }

        @include middleScreen {
          font-size: 24px;

        }
      }

      &:last-child {
        @include desktops {
          font-size: 16px;
        }

        @include smallScreen {
          font-size: 24px;

        }

        @include middleScreen {
          font-size: 28px;

        }

      }
    }

    h2.fadeInElement.show {
      &:first-child {
        @include fadeAndMoveDownAnimation
      }

      &:last-child {
        @include fadeAndMoveUpAnimation
      }
    }
  }

  .text {
    font-size: 16px;

    @include desktops {
      right: 10%;
    }

    p {
      @include desktops {
        font-size: 12px;
        color: #fff;
      }

      @include smallScreen {
        font-size: 16px;

      }

      @include middleScreen {
        font-size: 20px;

      }
    }

    p.fadeInElement.show {
      &:first-child {
        @include fadeAndMoveUpAnimation(.2s)
      }

      &:last-child {
        @include fadeAndMoveUpAnimation(.4s)
      }
    }
  }

  .pic {
    width: 100%;
    overflow: auto;

    img {
      width: 1000px;

      @include desktops {
        width: 100%;
      }
    }
  }

  >p {
    height: 100px;
    width: 100px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    bottom: 20px;
    background: #000;
    color: #fff;
    border-radius: 50%;

    @include desktops {
      display: none;
    }
  }
}
</style>
