<template>
  <div class="container-fluid" id="projects">

    <div class="row">

        <h2 class="display-3 text-white fadeInUp secHeading mt-4">Projects</h2>
    
    </div>

    <div class="row">

        <ul class="nav nav-pills d-flex justify-content-center mt-4" id="pills-tab" role="tablist">
                  <li class="nav-item" role="presentation">
                    <button class="nav-link text-white show active" id="pills-all-tab" data-bs-toggle="pill" data-bs-target="#pills-all" type="button" role="tab" aria-controls="pills-all" aria-selected="true">All</button>
                  </li>
                  <li class="nav-item" role="presentation">
                    <button class="nav-link text-white" id="pills-artwork-tab" data-bs-toggle="pill" data-bs-target="#pills-artwork" type="button" role="tab" aria-controls="pills-artwork" aria-selected="false">Digital Artwork</button>
                  </li>
                  <li class="nav-item" role="presentation">
                    <button class="nav-link text-white" id="pills-advert-tab" data-bs-toggle="pill" data-bs-target="#pills-advert" type="button" role="tab" aria-controls="pills-advert" aria-selected="false">Advertisement</button>
                  </li>
                  <li class="nav-item" role="presentation">
                    <button class="nav-link text-white" id="pills-design-tab" data-bs-toggle="pill" data-bs-target="#pills-design" type="button" role="tab" aria-controls="pills-design" aria-selected="false">Design</button>
                  </li>
    </ul>

    <div class="tab-content" id="pills-tabContent">

    <!-- All Projects -->
    <div class="tab-pane fade show active" id="pills-all" role="tabpanel" aria-labelledby="pills-all-tab">

    <div class="row projectsDiv" v-if="projects?.length">
                      <!-- Desktop cards -->
                

                <card v-for="project in projects" :key="project.id" class="cardDkt col-6">
                    <template #cardImg>
                    <img :src="project.img_url" :alt="project.projectName" loading="eager" class="img-fluid card-img-top">
                    </template>
                    <template #cardOverlay>
                    
                    <h5 class="card-title">{{ project.projectName }}
                    </h5>
                    
                    </template>
                </card>


    </div>
    </div>

    </div>
    
    
  </div>
</div>
</template>

<script setup>
import Card from './Card.vue'
import { computed, onMounted } from 'vue'
import { useStore } from 'vuex'
    const store = useStore()
    const projects = computed(() => store.state.projects)
    
    onMounted(() => {
      setTimeout(()=>{
        store.dispatch('fetchProjects')
      }, 1000)
    })

</script>

<style>

</style>