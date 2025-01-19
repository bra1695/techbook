<template>
  <div class="container p-3.5 sm:px-4 md:px-8 lg:px-32 xl:px-32 mx-auto my-2">
    <div class="container p-3.5 sm:px-4 md:px-8 lg:px-32 xl:px-32 mx-auto my-2">

    <div class="flex justify-center flex-row space-x-1">
        <img :src="iconStar" />
        <img :src="iconStar" />
        <img :src="iconStar" />
        <img :src="iconStar" />
        <img :src="iconStar" />
   </div>
   <div
      class='flex max-w-[343px] mt-6 flex-col gap-400 md:max-w-[704px] lg:max-w-full lg:text-center'>
      <p
        class='font-martian-mono text-preset-3-mobile text-neutral-900 md:text-preset-3'>
        "This book club transformed my technical reading from a solitary
        activity into an enriching community experience. The discussions are
        gold!"
      </p>
      <span class='text-preset-5 mt-4 text-neutral-700'
        >Sarah Chen, Software Architect</span
      >
    </div>
</div>
  </div>
</template>
<script>
  import iconStar from '@/assets/images/icon-star.svg';
  export default{
    data(){
        return{
            iconStar
        }
    }
  }


</script>