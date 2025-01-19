<template>
    <footer
      class="relative h-[541px] rounded-t-2xl bg-neutral-900 px-5 pt-24 text-white md:h-[505px]"
    >
      <!-- Background grid -->
      <div
        class="absolute inset-0 container-footer"
      ></div>
  
      <!-- Content -->
      <div
        class="relative mx-auto max-w-[343px] md:max-w-[704px] lg:max-w-[753px]"
      >
        <div class="space-y-8">
          <h2 class="text-center text-2xl font-bold lg:text-3xl">
            Ready to debug your reading list?
          </h2>
          <div class="mx-auto max-w-[388px] space-y-8">
            <div class="flex flex-col space-y-2">
                <button class="bg-transparent flex flex-row text-dark-navy px-4 py-4 border-2 w-96 border-[#182A4A] rounded-lg ">
                    REVIEW MEMBERSHIP OPTIONS <img :src="iconArrowUp" />
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
      </div>
  
      <!-- Footer bottom section -->
      <div
        class="relative mx-auto mt-20 flex flex-col items-center gap-5 border-t border-neutral-100 px-6 py-8 md:flex-row md:justify-between lg:max-w-[1170px]"
      >
        <span>&copy; 2024 – Tech Book Club</span>
        <div class="flex gap-6">
          <img
            :src="blueskyLogo"
            width="22"
            height="22"
            alt="Bluesky logo"
            class="h-5 w-5"
          />
          <img
            :src="linkedinLogo"
            width="22"
            height="22"
            alt="LinkedIn logo"
            class="h-5 w-5"
          />
        </div>
      </div>
    </footer>
  </template>
  
  <script >
  import blueskyLogo from '@/assets/images/logo-bluesky.svg'; // Adjust the path
  import linkedinLogo from '@/assets/images/logo-linkedin.svg'; // Adjust the path
  import iconArrowUp from '@/assets/images/icon-arrow-up.svg';
  import iconStar from '@/assets/images/icon-star.svg';
  import imageAvatar from "@/assets/images/image-avatars.webp";

  export default{
    data(){
        return {
            blueskyLogo,
            linkedinLogo,
            iconArrowUp,
            iconStar,
            imageAvatar
        }
    }
  }
  </script>
  
  <style scoped>
   .container-footer {
  background-image: url("@/assets/images/pattern-dark-bg.svg"); 
  background-size: cover; 
  background-position: center; 
  background-repeat: no-repeat; 
}
  </style>