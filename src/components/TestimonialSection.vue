<template>
  <div class="container-fluid">
    <div class="row">

      <h2 class="display-3 text-white fadeInUp secHeading mt-2 mb-3">Testimonials</h2>

    </div> 
    <div class="row testimonialSection mx-auto">

      <div class="testimonialCard" v-if="testimonials?.length">
        <MobileCard v-for="testimonial in testimonials" :key="testimonial.id" class="testimonial">
        <template #cardHeader>
          <img :src="testimonial.img_url" :alt="testimonial.Name" loading="eager" class="img-fluid">
        </template>
        <template #cardBody>
          <p>{{ testimonial.testimonial }}</p>
          <h3>{{ testimonial.Name }}</h3>
        </template>
      </MobileCard>
      </div>
      

    </div>
  </div>
</template>

<script setup>
import MobileCard from './MobileCard.vue';
import { computed, onMounted } from 'vue'
import { useStore } from 'vuex'
    const store = useStore()
    const testimonials = computed(() => store.state.testimonials )
    
    onMounted(() => {
      setTimeout(()=>{
        store.dispatch('fetchTestimonials')
      }, 1000)
    })
</script>

<style>

</style>