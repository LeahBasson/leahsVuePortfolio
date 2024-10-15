<template>
    <div class="container-fluid">
        <div class="row" id="topSection">
            <h2 class="display-3 text-white secHeading" data-aos="fade-up"  data-aos-duration="2000">Badges</h2>
        </div>

        <div class="row" id="bagde-listing" v-if="bagdes">
            <div class="bagde-view" data-bs-toggle="modal" data-bs-target="#osbModal" data-aos="fade-up"  data-aos-duration="2000">
                <img :src="bagdes[0].bagde" :alt="bagdes[0].title" loading="eager" class="img-fluid bagde-image">
                 <h2>{{  bagdes[0].title }}</h2>
            </div>
            <osbModal />
            <div class="bagde-view" data-bs-toggle="modal" data-bs-target="#linuxModal" data-aos="fade-up"  data-aos-duration="2000">
                <img :src="bagdes[1].bagde" :alt="bagdes[0].title" loading="eager" class="img-fluid bagde-image">
                <h2>{{  bagdes[1].title }}</h2>
            </div>
            <linuxModal />
        </div>
        <Spinner v-else/>

    </div>
</template>

<script setup>
import AOS from 'aos';
import osbModal from '@/components/osbModal.vue'
import linuxModal from '@/components/linuxModal.vue'
import Spinner from './Spinner.vue'
  import { computed, onMounted } from 'vue'
  import { useStore } from 'vuex'
  const store = useStore()
  const bagdes = computed(() => store.state.bagdes)

  onMounted(() => {
    setTimeout(()=>{
      store.dispatch('fetchBagdes')
    }, 1000);
    AOS.init();
  })
</script>

<style>
/* Badge Section */
#topSection{
    background-color: var(--primary);
    padding-top: 5rem;
}

#bagde-listing{
    display: flex;
    gap: 35rem;
    justify-content: center;
    background-color: var(--primary);
}

#bagde-listing h2{
    color: var(--secondary);
    font-family: "Poppins", sans-serif;
    font-weight: 400;
    padding-top: 2rem;
}

.bagde-view:hover{
    transform: translateY(-10px);
    transition: transform 0.5s ease-in-out;
}

.bagde-view {
    width: 22rem;
    transition: transform 0.5s ease-in-out;
    cursor: pointer;
}

.bagde-image{
    width: 14rem;
    margin-top: 3rem;
}

/* Media query */
@media (width < 999px)
{
    #bagde-listing{
    display: flex;
    gap: 2rem;
    justify-content: center;
    background-color: var(--primary);
}

    .bagde-view{
    width: 65%; 
}
.intro-image{
    width: 100%;
}

}
</style>