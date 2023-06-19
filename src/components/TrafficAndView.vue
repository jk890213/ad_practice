<template>
  <section>
    <div class="container">

      <div class="title">
        <h2 class="fadeInElement">Vision of The World</h2>
        <h2 class="fadeInElement">世界眼界 東⻄交匯</h2>
      </div>
      <div class="text">
        <p class="fadeInElement">信義新蘆雙捷 生活的速度</p>
        <p class="fadeInElement">
          中山北⺠生東雙軸心，跨界領域，近鄰中山北路、南京東路星級酒店聚落，晶華、國賓、老爺與大倉久和飯店等，繁華川流不息，雙城街、錦州街深夜食堂到米其林隨手可得。
          捷運紅線「雙連站」與黃線「中山國小站」悠遊雙北，回家步行不疾不徐，剛剛好的距離!生活便利，享增質的睿智之選。</p>
      </div>
      <div class="view">
        <div class="feature" v-for="view in views" :key="view.title">
          <div class="pic">
            <img :src="(view.imgUrl)" alt="">
          </div>
          <div class="text">
            <h3>{{ view.title }}</h3>
            <p>{{ view.content }}</p>
          </div>

        </div>
      </div>
    </div>
  </section>
</template>
  
<script setup lang="ts">
import img1 from '@/assets/images/neighbor_view/s3-1.jpg'
import img2 from '@/assets/images/neighbor_view/s3-5.jpg'
import img3 from '@/assets/images/neighbor_view/s3-4.jpg'
import img4 from '@/assets/images/neighbor_view/s3-2.jpg'

const views = [
  {
    imgUrl: img1,
    title: '永盛公園 永恆綠意',
    content: '樹的微笑、風的律動，天與地的默契，家在永盛公園旁，喜鵲築巢、樹風輕拂，住的舒適，過的繁華，為自己留一座都會新境，生活的發條鬆一點，心靈的空間輕一點。'
  },
  {
    imgUrl: img2,
    title: '都心森活 左右逢源',
    content: '近鄰新光三越、南西誠品、台北光點與赤峰街等，往圓山花博與南京松江也不遠，座落中山國小與新興國中學區，休閒與都會、商業與人文並蓄，機能豐沛，百年古蹟藝術聚落，信步探索生活靈光。'
  },
  {
    imgUrl: img3,
    title: '精品大道 時代風華',
    content: '雍容精品饗宴，星級酒店為鄰，轉身接軌巴黎、紐約、米蘭，生活散步像是都會舞步。匯聚世界精品，盛裝優雅日常時光，引領國際潮流，孕育有故事的傳奇街區，繁華生活以我為中心。 '
  },
  {
    imgUrl: img4,
    title: '林蔭官道 傳世眼界',
    content: '40米中山北路楓香林蔭，曾是外國元首來訪時必經之路，有「外交大道」之稱， 出門直取中山北路&⺠生東路，官道百年繁華流域，首都頂尖富域之地，精品風華永傳不息。'
  },
]
</script>
  
<style lang="scss" scoped>
section {
  padding: 0 12px;
  margin-bottom: 48px;

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
      // display: flex;
    }

    @include smallScreen {
      max-width: 1140px;
    }

    @include middleScreen {
      max-width: 1320px;
    }

    .title {
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
      margin-bottom: 20px;

      p.fadeInElement.show {
        &:first-child {
          @include fadeAndMoveUpAnimation(.2s)
        }

        &:last-child {
          @include fadeAndMoveUpAnimation(.4s)
        }
      }
    }

    .view {
      width: 100%;

      .feature{
        .text{
          margin: 10px 0;
        }

        img {
          width: 100%;
        }
      }

    }
  }
}
</style>
  