<template>
    <div
      :class="[
        'relative z-0 mx-auto flex h-[358px] w-[340px] flex-col gap-10 rounded-lg border border-neutral-200 p-6 lg:w-[286px]',
        { 'bg-neutral-100 lg:h-[390px] lg:w-[350px] lg:py-12': bestValue },
      ]"
    >
      <!-- bg decoration for bestValue card -->
      <div
        v-if="bestValue"
        class="absolute inset-0 bottom-0 right-0 -z-10 container-membership"
      ></div>
  
      <div class="space-y-6">
        <h3 class="text-xl font-semibold">{{ option }}</h3>
        <div v-if="price" class="flex items-center gap-2">
          <span class="text-lg font-bold">${{ price }}</span>
          <span class="text-sm text-neutral-700">/month</span>
        </div>
        <span v-else class="inline-block text-lg font-bold">Custom</span>
  
        <div class="w-full border border-neutral-200"></div>
  
        <div class="space-y-4">
            <div class="flex items-center gap-[14px]">
          <img :src="check" alt="Check icon" />
          <p class="text-preset-5 text-neutral-700">
            {{ firstCheckbox }}
          </p>
        </div>
        <div class="flex items-center gap-[14px]">
          <img :src="check" alt="Check icon" />
          <p class="text-preset-5 text-neutral-700">
            {{ secondCheckbox }}
          </p>
        </div>    
        </div>
      </div>
      <button class="bg-transparent flex items-center justify-center text-center flex-row text-dark-navy px-4 py-4 border-2 w-48 border-[#182A4A] rounded-lg ">
        {{ ctaText }}
      </button>
    </div>
  </template>
  <script >
  import check from "@/assets/images/icon-check.svg"
  export default{
    data(){
      return {
        check
      }
    },
    props:{
        option: {
      type: String,
      required: true,
    },
    firstCheckbox: {
      type: String,
      required: true,
    },
    secondCheckbox: {
      type: String,
      required: true,
    },
    bestValue: {
      type: Boolean,
      default: false,
    },
    price: {
      type: String,
      default: '',
    },
    ctaText: {
      type: String,
      default: 'Subscribe now',
    },
    }
  }

  </script>
  
  <style scoped>
 .container-membership {
  background-image: url("@/assets/images/pattern-glow.svg"); 
  background-size: cover; 
  background-position: center; 
  background-repeat: no-repeat; 
}
  </style>