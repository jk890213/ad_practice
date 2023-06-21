<template>
  <Banner />
  <AwardsCarousel />
  <DescriptionSection />
  <LocationPicture />
  <TrafficAndView />
  <PlanningAndInheritance />
  <FeatureSection />
  <BuildingStyle />
  <footer></footer>
  <MobileNav />
</template>

<script setup lang="ts">
import Banner from "@/components/Banner.vue";
import AwardsCarousel from "@/components/AwardsCarousel.vue";
import MobileNav from "@/components/MobileNav.vue";
import DescriptionSection from "@/components/DescriptionSection.vue";
import LocationPicture from "@/components/LocationPicture.vue";
import TrafficAndView from "@/components/TrafficAndView.vue";
import PlanningAndInheritance from "@/components/PlanningAndInheritance.vue";
import FeatureSection from "@/components/FeatureSection.vue";
import BuildingStyle from "@/components/BuildingStyle.vue";
import { onMounted } from "vue";

onMounted(() => {
  const observer = new IntersectionObserver(callback);
  const fadeInElement = document.querySelectorAll(".fadeInElement");
  if (fadeInElement.length) {
    fadeInElement.forEach((ele) => {
      observer.observe(ele);
    });
  }
});
const callback = (entries: any[], observer: IntersectionObserver) => {
  entries.forEach((entry) => {
    if (entry.isIntersecting) {
      entry.target.classList.add("show");
      observer.unobserve(entry.target);
    }
  });
};
</script>

<style lang="scss">
.fadeInElement {
  opacity: 0;
}

footer {
  height: 1000px;
}
</style>
