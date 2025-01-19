<template>
  <div class="container p-3.5 sm:px-4 md:px-8 lg:px-32 xl:px-32 mx-auto my-2">
    <div
      class="grid grid-rows-2 grid-cols-1 lg:grid-cols-2 gap-8 lg:grid-rows-1 mt-4 lg:mt-16"
    >
      <div class="flex flex-col justify-center">
        <h2
          class="max-w-[343px] text-preset-2-mobile text-neutral-900 md:max-w-[534px] md:text-preset-2"
        >
          Not your average book
          <span
            class="relative inline-block h-[46.53px] w-[108.62px] md:h-[68.08px] md:w-[158.9px]"
            >club
            <span class="absolute inset-0 -translate-x-[11px]"
              ><img :src="patternCircle" alt="Circle pattern" />
            </span>
          </span>
        </h2>
        <p class="text-[17px] tracking-[0.012em] text-neutral-700">
          Connect with a community that speaks your language - from
          <span class="text-preset-5-semibold">Python</span> to
          <span class="text-preset-5-semibold">TypeScript</span> and everything
          in between. Our discussions blend technical depth with practical
          applications.
        </p>
      </div>
      <div class="relative">
        <img :src="currentImage" alt="Image read" class="w-full overflow-hidden rounded-2xl" />
        <div
    class='absolute bottom-[50px] right-[82.44px] z-10 hidden h-[138px] w-[119px] md:inline-block lg:bottom-[31px] lg:right-[590.44px]'>
    <img :src=logoTech alt='Tech logos' />
  </div>
      </div>

    </div>
  </div>
</template>
<script>
import patternCircle from "@/assets/images/pattern-circle.png";
import imgNotAvgDesktop from "@/assets/images/image-not-average-desktop.webp";
import imgNotAvgTablet from "@/assets/images/image-not-average-tablet.webp";
import imgNotAvgMobile from "@/assets/images/image-not-average-mobile.webp";
import logoTech from '@/assets/images/logos-tech.svg';
export default {
  data() {
    return {
      patternCircle,
      imgNotAvgMobile,
      imgNotAvgTablet,
      imgNotAvgDesktop,
      currentImage: imgNotAvgDesktop,
      logoTech
    };
  },
  methods: {
    updateImage() {
      const screenWidth = window.innerWidth;
      if (screenWidth >= 1024) {
        // Desktop
        this.currentImage = this.imgNotAvgDesktop;
      } else if (screenWidth >= 768) {
        // Tablet
        this.currentImage = this.imgNotAvgTablet;
      } else {
        // Mobile
        this.currentImage = this.imgNotAvgMobile;
      }
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
  },
};
</script>
