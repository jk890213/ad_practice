<template>
  <section class="wrapper">
    <div class="container">
      <div class="text">
        <h1>{{ article.title }}</h1>
        <p>{{ article.text }}</p>
        <h2>{{ article.subTitle }}</h2>
        <p v-for="txt in article.awards" :key="txt">{{ txt }}</p>
      </div>
      <a-carousel effect="fade" :beforeChange="changeDescription" autoplay>
        <div><img src="@/assets/images/awards/ad1.jpg" alt="" /></div>
        <div><img src="@/assets/images/awards/ad8.jpg" alt="" /></div>
        <div><img src="@/assets/images/awards/ad9.jpg" alt="" /></div>
      </a-carousel>
    </div>
  </section>
</template>

<script setup lang="ts">
import { reactive } from "vue";

const des = [
  {
    title: "藝術之都捎來喜訊",
    text: "協律以「中山簡美」，2023巴黎設計大獎捷報！分別以建築公設與實品屋榮獲設計殊榮，肯定本案從建築規劃、美學工藝、設計選材、空間創造與居家營造等，用心鑄造經典篇章。",
    subTitle: "雙料大獎，閃耀國際：",
    awards: [
      "中山簡美 - 建築公設：榮獲「銀獎」",
      "中山簡美 - 實品屋：榮獲「銀獎」",
    ],
  },
  {
    title: "賀榮獲設計界繆思殊榮 再囊括二金一銀",
    text: "美國謬思設計大獎（MUSE Design Awards），為國際設計舞台盛事之一，集結全球跨領域設計思維，發掘設計繆思為宗旨，成就設計新潮。「中山簡美」再獲國際獎殊榮，本案以建築公設、實品屋與接待中心榮獲二金一銀。協律匠作築新，在都會繁華與土地情懷之間，梳理居住者需求，結合當代設計之美，化繁為簡，從外觀、公設到居家空間，營造出簡約、溫馨、舒適的氛圍，創造家的美好愉悅與歸屬感。",
    subTitle: "國際獎項，榮耀綻放：",
    awards: [
      "建築公設：榮獲「銀獎」",
      "實品屋：榮獲「金獎」",
      "接待中心：榮獲「金獎」",
    ],
  },
  {
    title: "國際捷報接二連三",
    text: "「中山簡美」繼巴黎設計獎，近期又接獲柏林設計獎殊榮，捷報不斷！建築公設、實品屋與接待中心三項榮獲肯定，並肩國際視野與創新設計。協律匠心，不凡品味，精鑄一尺一寸，以美為土地落款，延續家族傳承使命。",
    subTitle: "國際獎項，好評肯定：",
    awards: [
      "中山簡美建築公設：榮獲「銀獎」",
      "中山簡美實品屋：榮獲「銀獎」",
      "中山簡美接待中心： 榮獲 「優選」",
    ],
  },
];

const article = reactive({
  showIndex: 0,
  title: des[0].title,
  subTitle: des[0].subTitle,
  text: des[0].text,
  awards: des[0].awards,
});

const desLength = des.length;
const changeDescription = () => {
  article.showIndex =
    article.showIndex + 1 < desLength ? article.showIndex + 1 : 0;
  article.title = des[article.showIndex].title;
  article.subTitle = des[article.showIndex].subTitle;
  article.text = des[article.showIndex].text;
  article.awards = des[article.showIndex].awards;
};
</script>

<style lang="scss" scoped>
.wrapper {
  padding: 0 12px;
  margin-bottom: 48px;
}

.container {
  font-family: "Noto Serif TC", sans-serif;
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
    border: 2px solid #0e4f31;
    display: flex;
    padding: 12px;
    align-items: center;
  }

  @include smallScreen {
    max-width: 1140px;
  }

  @include middleScreen {
    max-width: 1320px;
  }

  .text {
    margin-bottom: 8px;

    h1 {
      margin-bottom: 12px;
      font-size: 18px;
      font-weight: bold;
      color: #0e4f31;
    }

    h2,
    p {
      font-size: 15px;
    }

    p {
      margin-bottom: 0;

      &:nth-child(2) {
        margin-bottom: 16px;
      }
    }

    @include desktops {
      order: 1;
      padding: 12px;
    }
  }

  .ant-carousel {
    @include desktops {
      margin: 12px;
      width: 60%;
    }

    :deep div img {
      width: 100%;
    }
  }
}
</style>
