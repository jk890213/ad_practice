<template>
  <section>
    <div class="container">
      <div class="text">
        <div class="overview">
          <h2 class="pic fadeInElement">SRC全石材 經典雋永</h2>
          <h2 class="pic fadeInElement">機能美學 有風有光的家</h2>
          <h3 class="pic fadeInElement">2房2衛戶戶邊間 零虛坪雙面採光</h3>
          <p class="pic fadeInElement">
            「中山簡美」中山北與⺠生東交匯，基地約126坪，林森北綠蔭第一排，近鄰1200坪永盛公園，均質兩房，24到30坪的規劃，戶戶邊間採光，北市罕見！以安全、舒適及智慧的家，呼應當代生活與地段能量，以雋永設計琢磨土地，打造建築不凡身價。
          </p>
        </div>
        <div class="content">
          <h3>都會靈感、人文意象、生態向度的新現代住宅</h3>
          <div class="item" v-for="{ title, text } in items" :key="title">
            <p>
              <span>{{ title }}</span
              >{{ text }}
            </p>
          </div>
        </div>
      </div>
      <div class="pic">
        <img src="@/assets/images/building_style/s8.jpg" alt="" />
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const items = [
  {
    title: "多元性：",
    text: "發揮基地與環境特色，保留過往美好注入新風格。",
  },
  {
    title: "國際性：",
    text: "以國際當代語彙為譜，簡約雋永為本質。",
  },
  {
    title: "藝術性：",
    text: "歷久彌新的極簡風格建構當代意象，保有美感一致性。",
  },
  {
    title: "都會性：",
    text: "呼應永盛公園，融入優雅森活，內蘊鬧中取靜氣質。",
  },
  {
    title: "機能性：",
    text: "坪數規劃以小家庭為主的正兩房，空間模組化，風格自由選。",
  },
  {
    title: "效率性：",
    text: "一層四戶兩部電梯，使用便利，減少等待時間。",
  },
];
</script>

<style lang="scss" scoped>
.pic img {
  width: 100%;
}

section {
  margin-bottom: 48px;

  @include desktops {
    margin-bottom: 160px;
  }

  .container {
    @include desktops {
      display: flex;
      align-items: center;
    }
    .text {
      padding: 0 12px;
      font-family: "Noto Sans TC", sans-serif;
      letter-spacing: 2px;
      line-height: 2;

      @include desktops {
        min-width: 50%;
        padding: 0 5%;
        line-height: 1.5;
      }
    }

    .pic {
      @include desktops {
        min-width: 50%;
      }
    }
  }
}

h2 {
  margin: 0;
  font-size: 18px;

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

h3 {
  margin: 0;
  font-size: 16px;

  @include desktops {
    font-size: 14px;
  }

  @include smallScreen {
    font-size: 20px;
  }

  @include middleScreen {
    font-size: 22px;
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
.overview {
  margin-bottom: 32px;

  h2 + h3 {
    margin: 8px 0;
  }

  h2.show {
    @include fadeAndMoveUpAnimation();
  }

  h3.show {
    @include fadeAndMoveUpAnimation(0.2s);
  }

  p.show {
    @include fadeAndMoveUpAnimation(0.4s);
  }
}
.content {
  h3 {
    display: inline-block;
    padding-bottom: 4px;
    margin-bottom: 20px;
    border-bottom: 1px solid #333;
  }

  span {
    display: block;
    font-weight: bold;

    @include desktops {
      display: inline;
      font-weight: normal;
    }
  }
}
</style>
