<template>
  <Banner />
  <AwardsCarousel />
  <nav class="mobile_nav">
    <ul>
      <li><a href=""> 地圖導航 </a></li>
      <li><a href=""> 撥打電話 </a></li>
      <li><a href=""> Facebook </a></li>
      <li><a href=""> Line@ </a></li>
    </ul>
  </nav>

  <footer></footer>
</template>

<script setup lang="ts">
import Banner from "@/components/Banner.vue";
import AwardsCarousel from "@/components/AwardsCarousel.vue";
</script>

<style lang="scss" scoped>
.mobile_nav {
  height: 60px;
  width: 100%;
  position: fixed;
  bottom: 0;

  @include desktops {
    display: none;
  }

  ul {
    height: 100%;
    display: flex;

    li {
      flex-grow: 1;
      background-color: #325e46;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      a {
        color: #fff;
        text-decoration: none;
      }
    }

    li + li {
      border-left: 1px solid #fff;
    }
  }
}

footer {
  height: 200px;
}
</style>
