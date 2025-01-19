<template>
    <div class="container p-3.5 sm:px-4 md:px-8 lg:px-32 xl:px-32 mx-auto my-2">
      <div>
        <img :src="logo" alt="Logo Tech Book" />
      </div>
      <div class="grid grid-rows-2  grid-cols-1 lg:grid-cols-2 lg:grid-rows-1 mt-4 lg:mt-16 ">
        <div class="flex items-center justify-center">
          <div class="space-y-8">
            <h1
              class="bg-text-gradient bg-clip-text text-preset-1-mobile text-transparent md:text-preset-1"
            >
              Join the ultimate tech book club
            </h1>
            <p class="text-preset-5 text-neutral-700">
              Turn your reading time into learning time with fellow tech
              enthusiasts. Get curated recommendations, join vibrant discussions,
              and level up your skills one chapter at a time.
            </p>
            <div class="flex flex-col space-y-2">
                <button class="bg-transparent flex flex-row text-dark-navy px-4 py-4 border-2 w-96 border-[#182A4A] rounded-lg ">
                    REVIEW MEMBERSHIP OPTIONS <img :src="iconArrowDown" />
                </button>
                <div class="flex flex-row">
                    <img class="h-[40px] w-[110px]" :src="imageAvatar" alt="Image Avatar" />
                    <div class="flex flex-col justify-center">
                        <div class="flex flex-row space-x-1">
                            <img :src="iconStar" />
                            <img :src="iconStar" />
                            <img :src="iconStar" />
                            <img :src="iconStar" />
                            <img :src="iconStar" />
                        </div>
                        <p class='font-martian-mono text-preset-7'>200+ developers joined already</p>
                    </div>
                    
                </div>

            </div>
          </div>
        </div>
        <div>
          <!-- Dynamic image based on screen size -->
          <img  :src="currentImage" alt="Hero Image" class="w-full overflow-hidden rounded-[5.08px]" />
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import logo from "@/assets/images/logo.svg";
  import heroDesktop from "@/assets/images/image-hero-desktop.webp";
  import heroMobile from "@/assets/images/image-hero-mobile.webp";
  import heroTablet from "@/assets/images/image-hero-tablet.webp";
  import imageAvatar from "@/assets/images/image-avatars.webp";
  import iconArrowDown from '@/assets/images/icon-arrow-down.svg';
  import iconStar from '@/assets/images/icon-star.svg';

  export default {
    data() {
      return {
        logo,
        heroDesktop,
        heroMobile,
        heroTablet,
        imageAvatar,
        iconStar,
        iconArrowDown,
        currentImage: heroDesktop, // Default image
      };
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
    methods: {
      updateImage() {
        const screenWidth = window.innerWidth;
        if (screenWidth >= 1024) {
          // Desktop
          this.currentImage = this.heroDesktop;
        } else if (screenWidth >= 768) {
          // Tablet
          this.currentImage = this.heroTablet;
        } else {
          // Mobile
          this.currentImage = this.heroMobile;
        }
      },
    },
  };
  </script>
  
  <style scoped>
.container {
  background-image: url("@/assets/images/pattern-light-bg.svg"); 
  background-size: cover; 
  background-position: center; 
  background-repeat: no-repeat; 
}
  </style>