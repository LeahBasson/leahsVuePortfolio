<template>
    <div class="container-fluid">
        <div class="row" id="topSection">
            <h2 class="display-3 text-white secHeading" data-aos="fade-up"  data-aos-duration="2000">Badges</h2>
        </div>

        <div class="row" id="bagde-listing" v-if="bagdes">
            <div class="bagde-view" data-bs-toggle="modal" data-bs-target="#osbModal" data-aos="fade-up"  data-aos-duration="2000">
                <img :src="bagdes[0].bagde" :alt="bagdes[0].title" loading="eager" class="img-fluid bagde-image">
                 <h3>{{  bagdes[0].title }}</h3>
            </div>
            <osbModal />
            <div class="bagde-view" data-bs-toggle="modal" data-bs-target="#linuxModal" data-aos="fade-up"  data-aos-duration="2000">
                <img :src="bagdes[1].bagde" :alt="bagdes[1].title" loading="eager" class="img-fluid bagde-image">
                <h3>{{  bagdes[1].title }}</h3>
            </div>
            <linuxModal />
            <div class="bagde-view" data-bs-toggle="modal" data-bs-target="#CyberAnalystModal" data-aos="fade-up"  data-aos-duration="2000">
                <img :src="bagdes[2].bagde" :alt="bagdes[2].title" loading="eager" class="img-fluid bagde-image">
                <h3>{{  bagdes[2].title }}</h3>
            </div>
            <CyberAnalystModal />
        </div>
        <Spinner v-else/>

        <div class="row" id="bagde-listing" v-if="bagdes">

        <div class="bagde-view" data-bs-toggle="modal" data-bs-target="#UiAndUxModal" data-aos="fade-up"  data-aos-duration="2000">
                <img :src="bagdes[3].bagde" :alt="bagdes[3].title" loading="eager" class="img-fluid bagde-image">
                <h3>{{  bagdes[3].title }}</h3>
            </div>
            <UIAndUxModal />
            <div class="bagde-view" data-bs-toggle="modal" data-bs-target="#ScrumModal" data-aos="fade-up"  data-aos-duration="2000">
                <img :src="bagdes[4].bagde" :alt="bagdes[4].title" loading="eager" class="img-fluid bagde-image">
                <h3>{{  bagdes[4].title }}</h3>
            </div>
            <ScrumModal />
        </div>
    </div>
</template>

<script setup>
import AOS from 'aos';
import osbModal from '@/components/osbModal.vue'
import linuxModal from '@/components/linuxModal.vue'
import UIAndUxModal from './UIAndUxModal.vue';
import ScrumModal from './ScrumModal.vue';
import CyberAnalystModal from './CyberAnalystModal.vue'
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
    gap: 12rem;
    justify-content: center;
    background-color: var(--primary);
}

#bagde-listing h3{
    color: var(--secondary);
    font-family: "Poppins", sans-serif;
    font-weight: 400;
    padding-top: 2rem;
}

.bagde-view:hover{
    transform: translateY(-10px) !important;
    transition: transform 0.5s ease-in-out;
}

.bagde-view {
    width: 18rem;
    transition: transform 0.5s ease-in-out !important;
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