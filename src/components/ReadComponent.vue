<template>
  <div class="container p-3.5 sm:px-4 md:px-8 lg:px-32 xl:px-32 mx-auto my-2">
    <div
      class="grid grid-rows-2 grid-cols-1 lg:grid-cols-2 gap-8 lg:grid-rows-1 mt-4 lg:mt-16"
    >
      <div class="order-2 lg:order-1">
        <img :src="currentImage" alt="Image read" class="w-full overflow-hidden rounded-2xl" />
      </div>
      <div class="order-1 lg:order-2 space-y-[24px] flex flex-col  justify-center">
        <h2 class="text-preset-2-mobile text-neutral-900 md:text-preset-2">
          Read together, <br />
          grow together
        </h2>
        <div class="flex items-center gap-[14px]">
          <img :src="check" alt="Check icon" />
          <p class="text-preset-5 text-neutral-700">
            Monthly curated tech reads selected by industry experts
          </p>
        </div>
        <div class="flex items-center gap-[14px]">
          <img :src="check" alt="Check icon" />
          <p class="text-preset-5 text-neutral-700">
            Virtual and in-person meetups for deep-dive discussions
          </p>
        </div>
        <div class="flex items-center gap-[14px]">
          <img :src="check" alt="Check icon" />
          <p class="text-preset-5 text-neutral-700">
            Early access to new tech book releases
          </p>
        </div>
        <div class="flex items-center gap-[14px]">
          <img :src="check" alt="Check icon" />
          <p class="text-preset-5 text-neutral-700">
            Author Q&A sessions with tech thought leaders
          </p>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import imgReadDesktop from "@/assets/images/image-read-together-desktop.webp";
import imgReadTablet from "@/assets/images/image-read-together-tablet.webp";
import imgReadMobile from "@/assets/images/image-read-together-mobile.webp";
import check from "@/assets/images/icon-check.svg"
export default {
  data() {
    return {
      imgReadDesktop,
      imgReadTablet,
      imgReadMobile,
      check,
      currentImage: imgReadDesktop,
    };
  },
  methods: {
    updateImage() {
      const screenWidth = window.innerWidth;
      if (screenWidth >= 1024) {
        // Desktop
        this.currentImage = this.imgReadDesktop;
      } else if (screenWidth >= 768) {
        // Tablet
        this.currentImage = this.imgReadTablet;
      } else {
        // Mobile
        this.currentImage = this.imgReadMobile;
      }
    },
  },
  mounted() {
    // Set the initial image based on screen width
    this.updateImage();
    // Add a resize event listener to update the image dynamically
    window.addEventListener("resize", this.updateImage);
  },
  unmounted() {
    // Remove the resize event listener when the component is destroyed
    window.removeEventListener("resize", this.updateImage);
  },
};
</script>
