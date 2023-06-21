<template>
  <section>
    <div class="container">
      <div
        class="item"
        v-for="{ mainPic, decorationUrl, title, content } in items"
        :key="title"
      >
        <div class="text">
          <div class="pic fadeInElement">
            <img :src="decorationUrl" alt="" />
          </div>
          <h2 class="fadeInElement">{{ title }}</h2>
          <p class="fadeInElement">{{ content }}</p>
        </div>
        <div class="pic">
          <img :src="mainPic" alt="" />
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import decoration1 from "@/assets/images/feature/ill-14.png";
import decoration2 from "@/assets/images/feature/ill-15.png";
import decoration3 from "@/assets/images/feature/ill-13.png";
import decoration4 from "@/assets/images/feature/ill-16.png";
import img1 from "@/assets/images/feature/s7-1.jpg";
import img2 from "@/assets/images/feature/s7-2.jpg";
import img3 from "@/assets/images/feature/s7-3.jpg";
import img4 from "@/assets/images/feature/s7-4.jpg";

const items = [
  {
    mainPic: img1,
    decorationUrl: decoration1,
    title: "建築美學｜詠筑建築師事務所",
    content:
      "建築，是環境改造的大業，我們從土地街廓察覺，形隨機能，好住好用為本，感受到幸福，還有家的溫度。",
  },
  {
    mainPic: img2,
    decorationUrl: decoration2,
    title: "結構安全｜織本構造設計",
    content:
      "日商織本構造以百年建築為根基，專業的建築規劃團隊，鞏固安全根基。工匠職人細心刻劃世界級精工，強震來襲也不怕！安全守護家人與資產，建築堅固如山，如同經典作品，世代流傳。 日本專業技術的職人建築，超越半世紀的功力，領導全球建築安全。",
  },
  {
    mainPic: img3,
    decorationUrl: decoration3,
    title: "燈光設計｜億光智能科技",
    content:
      "全球LED領導品牌，打造智能、環保、節能、健康之照明物聯網方案，聰明便利高品質，提升燈光節能與生活品質。",
  },
  {
    mainPic: img4,
    decorationUrl: decoration4,
    title: "精品公設＆全裝修｜樂朵室內設計",
    content:
      "將生活美學與精緻品味帶入日常，為都會家庭增添溫暖感受，回家愜意放鬆。",
  },
];
</script>

<style lang="scss" scoped>
section {
  padding: 80px 12px;
  margin-bottom: 48px;
  background: #f1f1f1;

  @include desktops {
    margin-bottom: 160px;
  }

  .container {
    font-family: "Noto Sans TC", sans-serif;
    letter-spacing: 2px;
    margin: 0 auto;

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
  }
}

.pic img {
  width: 100%;
}

h2 {
  font-size: 18px;
  font-weight: bold;

  @include desktops {
    font-size: 18px;
  }

  @include smallScreen {
    font-size: 20px;
  }

  @include middleScreen {
    font-size: 30px;
  }
}

p {
  font-size: 15px;
  font-weight: bold;

  @include desktops {
    font-size: 12px;
    font-weight: normal;
  }

  @include smallScreen {
    font-size: 16px;
  }

  @include middleScreen {
    font-size: 20px;
  }
}
.item {
  margin-bottom: 30px;

  @include phone {
    font-size: 12px;
    font-weight: normal;
  }

  @include pad {
    font-size: 16px;
  }

  @include desktops {
    font-size: 16px;
    display: flex;
    align-items: center;
  }

  @include smallScreen {
    font-size: 16px;
  }

  @include middleScreen {
    font-size: 20px;
  }

  .text {
    @include desktops {
      width: 50%;
      padding: 0 12px;
    }

    .pic {
      margin-bottom: 8px;
      width: 20%;
    }

    .pic.show {
      @include bounceInAnimation();
    }
  }

  .pic {
    @include desktops {
      width: 50%;
      padding: 0 12px;
    }
  }

  h2.show {
    @include fadeAndMoveUpAnimation();
  }
  p.show {
    @include fadeAndMoveUpAnimation(0.2s);
  }
}
</style>
