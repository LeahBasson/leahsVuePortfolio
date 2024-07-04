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
          <div class="name"> 
            <h3>{{ testimonial.Name }}</h3>
          </div>  
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
#testimonials{
  background-color: var(--primary);
  font-family: "Montserrat", sans-serif;
}

#testimonials h2{
  margin-top: 5rem;
}

.testimonialCard{
  display: flex;
  background-color: transparent;
  justify-content: center;
  flex-wrap: wrap;
}

.testimonialSection{
  width: 86vw;
}

.testimonial {
  width: 30%;
  padding: 1rem;
  height: auto;
  margin: 13px;
  text-align: center;
  border: 2px solid var(--alternative);
  background-color: var(--secondary);
}

.testimonial img {
  width: 12rem;
  border-radius: 50%;
  margin-bottom: 10px;
  border: 1px solid var(--alternative);
}

.testimonial p {
  font-style: italic;
}

.testimonial h3 {
  margin: 0;
}

/* Media query */
@media (width < 999px)
{
  /* Testimonial Section */
.testimonialCard{
  display: flex;
  background-color: transparent;
  justify-content: center;
  flex-direction: column;
}

.testimonialSection{
  width: 82vw;
  background-color: transparent;
}

.testimonial {
  width: 100%;
  padding: 1rem;
  height: auto;
  margin: 0;
  text-align: center;
  border: 2px solid var(--alternative);
  background-color: var(--secondary);
  margin-top: 1rem;
}

.testimonial img {
  width: 12rem;
  border-radius: 50%;
  margin-bottom: 1rem;
  border: 1px solid var(--alternative);
}

.testimonial p {
  font-style: italic;
  font-size: 1rem;
  color: black;
}
}
</style>