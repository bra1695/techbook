<template>
<JoinComponent />
<ReadComponent />
<TechComponent />
<MembershipComponent />
<TestimonialComponent />
<FooterComponent />
</template>

<script>
import JoinComponent from './components/JoinComponent.vue';
import ReadComponent from './components/ReadComponent.vue';
import TechComponent from './components/TechComponent.vue';
import MembershipComponent from './components/MembershipComponent.vue';
import TestimonialComponent from './components/TestimonialComponent.vue';
import FooterComponent from './components/FooterComponent.vue';
export default {
  components:{
    JoinComponent,
    ReadComponent,
    TechComponent,
    MembershipComponent,
    TestimonialComponent,
    FooterComponent
  }
}
</script>