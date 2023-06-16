<template>
  <Banner />
  <AwardsCarousel />
  <MobileNav/>

  <footer></footer>
</template>

<script setup lang="ts">
import Banner from "@/components/Banner.vue";
import AwardsCarousel from "@/components/AwardsCarousel.vue";
import MobileNav from "@/components/MobileNav.vue";
import { onMounted } from "vue";

onMounted(() => {
  const observer = new IntersectionObserver(callback);
  const allImgs = document.querySelectorAll('.fadeInImg');
  if (allImgs.length) {
    allImgs.forEach((ele) => {
      observer.observe(ele)
    })
  }
})
const callback = (entries: any[], observer: IntersectionObserver) => {
  entries.forEach(entry => {
    console.log(entry.isIntersecting);
    console.log(entry.intersectionRatio);
    
    if (entry.isIntersecting && entry.intersectionRatio > 0) {
      entry.target.classList.add('show')
      observer.unobserve(entry.target);
    }
  });
}
</script>

<style lang="scss">
.fadeInImg {
  opacity: 0;
}

footer {
  height: 1000px;
}
</style>
