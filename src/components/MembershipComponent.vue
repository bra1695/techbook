<template>
  <div class="container p-3.5 sm:px-4 md:px-8 lg:px-32 xl:px-32 mx-auto my-2">
    <h2 class='text-center text-preset-2-mobile md:text-preset-2'>
      Membership options
    </h2>
    <div
      class='mx-auto grid grid-cols-1 place-items-center mt-16 gap-4 md:grid-cols-2 lg:grid-cols-3'>
      <!-- membership cards -->
      <div>
        <MembershipCard
          option='Starter'
          price='19'
          firstCheckbox='1 book/month'
          secondCheckbox='Online Forums'
        />
      </div>

      <div>
        <MembershipCard
          option='Pro'
          price='29'
          firstCheckbox='2 books/month'
          secondCheckbox='Virtual meetups'
          bestValue
        />
      </div>

      <div>
        <MembershipCard
          option='Enterprise'
          firstCheckbox='Team access'
          secondCheckbox='Private sessions'
          ctaText='Talk to us'
        />
      </div>
    </div>
  </div>
</template>
<script>
import MembershipCard from './MembershipCard.vue';
export default{
components:{
    MembershipCard
}
}
</script>