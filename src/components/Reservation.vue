<template>
  <section>
    <div class="container">
      <div class="text">
        <div class="pic fadeInElement">
          <img src="@/assets/images/reservation/logo3.svg" alt="" />
        </div>
        <div class="title">
          <h2 class="fadeInElement">SRC全石材X智能防疫X風格選全裝修</h2>
          <h3 class="fadeInElement">中山民生雙軸· 永盛公園旁</h3>
          <p class="fadeInElement">24-30坪 ｜均質2房2衛 零虛坪雙面採光</p>
        </div>
        <div class="content">
          <p class="fadeInElement" v-for="text in features" :key="text">
            {{ text }}
          </p>
        </div>
      </div>
      <div class="social_link">
        <div class="item fadeInElement" v-for="{ imgUrl, title, linkUrl } in links" :key="title">
          <a :href="linkUrl" target="_blank">
            <div>
              <div class="pic">
                <img :src="imgUrl" alt="">
              </div>
              <span>
                {{ title }}
              </span>
            </div>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import map from "@/assets/images/reservation/map.png";
import phone from "@/assets/images/reservation/phone.png";
import facebook from "@/assets/images/reservation/facebook.png";
import line from "@/assets/images/reservation/line.png";


const features = [
  "投資興建：協律有限公司",
  "建築美學：詠筑建築師事務所",
  "結構安全：織本構造設計",
  "精品公設：樂朵室內設計",
  "燈光設計：億光智能科技",
  "建照號碼：111建字第0181號",
];

const links = [{
  title: '地圖導航',
  imgUrl: map,
  linkUrl: 'https://bit.ly/3PC5EGa'
}, {
  title: '02-2567-4588',
  imgUrl: phone,
  linkUrl: 'tel:+886-2-25674588'
}, {
  title: 'Facebook',
  imgUrl: facebook,
  linkUrl: 'https://bit.ly/3oBWSMA'
}, {
  title: 'Line@',
  imgUrl: line,
  linkUrl: "https://lin.ee/B9sG5h7"
},]
</script>

<style lang="scss" scoped>
section {
  padding: 80px 12px;
  background-image: url("@/assets/images/reservation/bg2.jpg");

  .container {
    margin: 0 auto;
    font-family: "Noto Sans TC", sans-serif;

    @include phone {
      max-width: 540px;
    }

    @include pad {
      max-width: 720px;
    }

    @include desktops {
      max-width: 960px;
    }

    @include smallScreen {
      max-width: 1140px;
    }

    @include middleScreen {
      max-width: 1320px;
    }

    h2,
    h3,
    p {
      color: #727171;
    }

    h2 {
      margin: 0;
      font-size: 18px;

      @include desktops {
        font-size: 22px;
      }

      @include smallScreen {
        font-size: 28px;
      }

      @include middleScreen {
        font-size: 34px;
      }
    }

    h3 {
      margin: 0;
      font-size: 16px;

      @include desktops {
        font-size: 20px;
      }

      @include smallScreen {
        font-size: 26px;
      }

      @include middleScreen {
        font-size: 30px;
      }
    }

    p {
      font-size: 15px;

      @include desktops {
        font-size: 12px;
      }

      @include smallScreen {
        font-size: 16px;
      }

      @include middleScreen {
        font-size: 20px;
      }
    }
  }
}

.pic img {
  width: 100%;
}

.text {
  margin-bottom: 50px;

  .pic {
    width: 35%;
    margin: 0 auto 30px;

    @include desktops {
      width: 10%;
    }
  }

  .pic.show {
    @include fadeAndMoveUpAnimation();
  }

  .title,
  .content {
    text-align: center;
  }

  .title {
    margin-bottom: 30px;

    h2 {
      padding-bottom: 4px;
      display: inline-block;
      border-bottom: 1px solid #727171;
    }

    .fadeInElement.show {
      $itemLength: 3;

      @for $i from 1 through $itemLength {
        &:nth-child(#{$i}) {
          $ms: ($i + 1) * 0.1;
          @include fadeAndMoveUpAnimation(#{$ms}s);
        }
      }
    }
  }

  .content {
    .fadeInElement.show {
      $itemLength: 6;

      @for $i from 1 through $itemLength {
        &:nth-child(#{$i}) {
          $ms: ($i + 4) * 0.1;
          @include fadeAndMoveUpAnimation(#{$ms}s);
        }
      }
    }
  }
}

.social_link {
  display: none;

  @include desktops {
    display: flex;
    justify-content: space-around;

    .item {
      width: 16%;
      // padding: 48px 0;
      border: 1px solid #000;
      border-radius: 4px;
      text-align: center;

      .pic {
        margin: 0 auto;
        width: 40%;
      }

      span {
        font-size: 20px;
      }

      a {
        width: 100%;
        height: 100%;
        text-decoration: none;
        color: #000;

        >div {
          padding: 48px 0;
        }
      }
    }

    .item.show {
      @include bounceInAnimation();
    }
  }
}
</style>
