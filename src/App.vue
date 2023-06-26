<template>
  <Banner />
  <AwardsCarousel />
  <DescriptionSection />
  <LocationPicture />
  <TrafficAndView />
  <PlanningAndInheritance />
  <FeatureSection />
  <BuildingStyle />
  <Reservation />
  <GoogleMap />
  <MobileNav />
  <div id="reserve">
    <a href="#reserve_form">
      <img :src="btn" alt="">
    </a>
  </div>
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
import Reservation from "@/components/Reservation.vue";
import GoogleMap from "@/components/GoogleMap.vue";
import { onMounted } from "vue";
import btn from "@/assets/images/reservation/btn.jpg";

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
html{
  scroll-behavior: smooth;
}

.fadeInElement {
  opacity: 0;
}

#reserve {
  width: 48px;
  height: 48px;
  position: fixed;
  top: 50%;
  right: 0;
  transform: translateY(-50%);
  z-index: 10;

  @include desktops {
    width: 80px;
    height: 80px;
  }

  a, img{
    width: 100%;
  }
}
</style>
