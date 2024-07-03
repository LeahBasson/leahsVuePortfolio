<template>
  <div class="container-fluid" id="projects">

    <div class="row">

        <h2 class="display-3 text-white fadeInUp secHeading mt-4">Projects</h2>
    
    </div>

    <div class="row">

        <ul class="nav nav-pills d-flex justify-content-center mt-4 red" id="pills-tab" role="tablist">
                  <li class="nav-item" role="presentation">
                    <button class="nav-link text-white show active" id="pills-all-tab" data-bs-toggle="pill" data-bs-target="#pills-all" type="button" role="tab" aria-controls="pills-all" aria-selected="true">All</button>
                  </li>
                  <li class="nav-item" role="presentation">
                    <button class="nav-link text-white" id="pills-artwork-tab" data-bs-toggle="pill" data-bs-target="#pills-artwork" type="button" role="tab" aria-controls="pills-artwork" aria-selected="false">Digital Artwork</button>
                  </li>
                  <li class="nav-item" role="presentation">
                    <button class="nav-link text-white" id="pills-mini-project-tab" data-bs-toggle="pill" data-bs-target="#pills-mini-project" type="button" role="tab" aria-controls="pills-mini-project" aria-selected="false">Mini Project</button>
                  </li>
                  <li class="nav-item" role="presentation">
                    <button class="nav-link text-white" id="pills-logo-tab" data-bs-toggle="pill" data-bs-target="#pills-logo" type="button" role="tab" aria-controls="pills-logo" aria-selected="false">Logo</button>
                  </li>
                  <li class="nav-item" role="presentation">
                    <button class="nav-link text-white" id="pills-website-tab" data-bs-toggle="pill" data-bs-target="#pills-website" type="button" role="tab" aria-controls="pills-website" aria-selected="false">Website</button>
                  </li>
    </ul>

    <div class="tab-content center" id="pills-tabContent">

    <!-- All Projects -->
    <div class="tab-pane fade show active" id="pills-all" role="tabpanel" aria-labelledby="pills-all-tab">

    <div class="projectsDiv" v-if="projects?.length">
                <!-- Desktop cards -->     
                <card v-for="project in projects" :key="project.id" class="cardDkt">
                    <template #cardImg>
                    <img :src="project.img_url" :alt="project.projectName" loading="eager" class="img-fluid card-img-top">
                    </template>
                    <template #cardOverlay>
                    
                    <h5 class="card-title">{{ project.projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ project.description }}</p>

                    <div class="mt-4 buttons">
                      <a :href="project.gitHub" target="_blank" class="button btn-outline-card mx-2">Repo Link</a>
                      <a :href="project.vercel" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
                    </div>

                    </template>
                </card>         
              
    </div>

    <Spinner v-else/>

    <!-- Mobile Card -->
      
    <div class="Mobile" v-if="projects?.length">
                <MobileCard v-for="project in projects" :key="project.id" class="card mt-4">
                    <template #cardHeader>
                    <img :src="project.mobileImage" :alt="project.projectName" loading="eager" class="img-fluid">
                    </template>
                    <template #cardBody>
                    <h5 class="card-title">{{ project.projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ project.description }}</p>

                    <div class="mt-4 d-flex flex-column">
                      <a :href="project.gitHub" target="_blank" class="btnMobile mt-2">Repo Link</a>
                      <a :href="project.vercel" target="_blank" class="btnMobile mt-3">Hosted Link</a>
                    </div>

                    </template>
                </MobileCard>      
    </div>
    <Spinner v-else/>

    

    </div>

      <!-- Digital Artwork -->
      <div class="tab-pane fade" id="pills-artwork" role="tabpanel" aria-labelledby="pills-artwork-tab">

        <div class="projectsDiv" v-if="projects">
                <!-- Desktop cards -->     
                <card class="cardDkt">
                    <template #cardImg>
                    <img :src="projects[0].img_url" :alt="projects[0].projectName" loading="eager" class="img-fluid card-img-top">
                    </template>
                    <template #cardOverlay>
                    
                    <h5 class="card-title">{{ projects[0].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[0].description }}</p>

                    <div class="mt-4 buttons">
                      <a :href="projects[0].gitHub" target="_blank" class="button btn-outline-card mx-2">Repo Link</a>
                      <a :href="projects[0].vercel" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
                    </div>

                    </template>
                </card> 
                
                <card class="cardDkt">
                    <template #cardImg>
                    <img :src="projects[4].img_url" :alt="projects[4].projectName" loading="eager" class="img-fluid card-img-top">
                    </template>
                    <template #cardOverlay>
                    
                    <h5 class="card-title">{{ projects[4].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[4].description }}</p>

                    <div class="mt-4 buttons">
                      <a :href="projects[4].gitHub" target="_blank" class="button btn-outline-card mx-2">Repo Link</a>
                      <a :href="projects[4].vercel" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
                    </div>

                    </template>
                </card>  

                <card class="cardDkt">
                    <template #cardImg>
                    <img :src="projects[6].img_url" :alt="projects[6].projectName" loading="eager" class="img-fluid card-img-top">
                    </template>
                    <template #cardOverlay>
                    
                    <h5 class="card-title">{{ projects[6].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[6].description }}</p>

                    <div class="mt-4 buttons">
                      <a :href="projects[6].gitHub" target="_blank" class="button btn-outline-card mx-2">Repo Link</a>
                      <a :href="projects[6].vercel" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
                    </div>

                    </template>
                </card>  
              
                
        </div>

    <Spinner v-else/>

     <!-- Mobile Card -->
     <div v-if="projects?.length">

     <div class="Mobile">
                <MobileCard class="card mt-4">
                    <template #cardHeader>
                    <img :src="projects[0].img_url" :alt="projects[0].projectName" loading="eager" class="img-fluid">
                    </template>
                    <template #cardBody>
                    <h5 class="card-title">{{ projects[0].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[0].description }}</p>

                    <div class="mt-4 d-flex flex-column">
                      <a :href="projects[0].gitHub" target="_blank" class="btnMobile mt-2">Repo Link</a>
                      <a :href="projects[0].vercel" target="_blank" class="btnMobile mt-3">Hosted Link</a>
                    </div>

                    </template>
                </MobileCard>      
    </div>

    <div class="Mobile">
                <MobileCard class="card mt-4">
                    <template #cardHeader>
                    <img :src="projects[4].mobileImage" :alt="projects[4].projectName" loading="eager" class="img-fluid">
                    </template>
                    <template #cardBody>
                    <h5 class="card-title">{{ projects[4].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[4].description }}</p>

                    <div class="mt-4 d-flex flex-column">
                      <a :href="projects[4].gitHub" target="_blank" class="btnMobile mt-2">Repo Link</a>
                      <a :href="projects[4].vercel" target="_blank" class="btnMobile mt-3">Hosted Link</a>
                    </div>

                    </template>
                </MobileCard>      
    </div>

    <div class="Mobile">
                <MobileCard class="card mt-4">
                    <template #cardHeader>
                    <img :src="projects[6].mobileImage" :alt="projects[6].projectName" loading="eager" class="img-fluid">
                    </template>
                    <template #cardBody>
                    <h5 class="card-title">{{ projects[6].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[6].description }}</p>

                    <div class="mt-4 d-flex flex-column">
                      <a :href="projects[6].gitHub" target="_blank" class="btnMobile mt-2">Repo Link</a>
                      <a :href="projects[6].vercel" target="_blank" class="btnMobile mt-3">Hosted Link</a>
                    </div>

                    </template>
                </MobileCard>      
    </div>

  </div>
    <Spinner v-else/>

      </div>

        <!-- Mini Project -->
        <div class="tab-pane fade" id="pills-mini-project" role="tabpanel" aria-labelledby="pills-mini-project-tab">
          <div class="projectsDiv" v-if="projects">

            <!-- Desktop cards -->     
            <card class="cardDkt">
                    <template #cardImg>
                    <img :src="projects[5].img_url" :alt="projects[5].projectName" loading="eager" class="img-fluid card-img-top">
                    </template>
                    <template #cardOverlay>
                    
                    <h5 class="card-title">{{ projects[5].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[5].description }}</p>

                    <div class="mt-4 buttons">
                      <a :href="projects[5].gitHub" target="_blank" class="button btn-outline-card mx-2">Repo Link</a>
                      <a :href="projects[5].vercel" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
                    </div>

                    </template>
            </card> 

            <card class="cardDkt">
                    <template #cardImg>
                    <img :src="projects[3].img_url" :alt="projects[3].projectName" loading="eager" class="img-fluid card-img-top">
                    </template>
                    <template #cardOverlay>
                    
                    <h5 class="card-title">{{ projects[3].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[3].description }}</p>

                    <div class="mt-4 buttons">
                      <a :href="projects[3].gitHub" target="_blank" class="button btn-outline-card mx-2">Repo Link</a>
                      <a :href="projects[3].vercel" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
                    </div>

                    </template>
            </card> 

            <card class="cardDkt">
                    <template #cardImg>
                    <img :src="projects[2].img_url" :alt="projects[2].projectName" loading="eager" class="img-fluid card-img-top">
                    </template>
                    <template #cardOverlay>
                    
                    <h5 class="card-title">{{ projects[2].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[2].description }}</p>

                    <div class="mt-4 buttons">
                      <a :href="projects[2].gitHub" target="_blank" class="button btn-outline-card mx-2">Repo Link</a>
                      <a :href="projects[2].vercel" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
                    </div>

                    </template>
            </card> 

          </div>
          <Spinner v-else/>

          <!-- Mobile Card -->
     <div v-if="projects?.length">

      <div class="Mobile">
                <MobileCard class="card mt-4">
                    <template #cardHeader>
                    <img :src="projects[5].mobileImage" :alt="projects[5].projectName" loading="eager" class="img-fluid">
                    </template>
                    <template #cardBody>
                    <h5 class="card-title">{{ projects[5].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[5].description }}</p>

                    <div class="mt-4 d-flex flex-column">
                      <a :href="projects[5].gitHub" target="_blank" class="btnMobile mt-2">Repo Link</a>
                      <a :href="projects[5].vercel" target="_blank" class="btnMobile mt-3">Hosted Link</a>
                    </div>

                    </template>
                </MobileCard>      
    </div>

    <div class="Mobile">
                <MobileCard class="card mt-4">
                    <template #cardHeader>
                    <img :src="projects[3].mobileImage" :alt="projects[3].projectName" loading="eager" class="img-fluid">
                    </template>
                    <template #cardBody>
                    <h5 class="card-title">{{ projects[3].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[3].description }}</p>

                    <div class="mt-4 d-flex flex-column">
                      <a :href="projects[3].gitHub" target="_blank" class="btnMobile mt-2">Repo Link</a>
                      <a :href="projects[3].vercel" target="_blank" class="btnMobile mt-3">Hosted Link</a>
                    </div>

                    </template>
                </MobileCard>      
    </div>

    <div class="Mobile">
                <MobileCard class="card mt-4">
                    <template #cardHeader>
                    <img :src="projects[2].mobileImage" :alt="projects[2].projectName" loading="eager" class="img-fluid">
                    </template>
                    <template #cardBody>
                    <h5 class="card-title">{{ projects[2].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[2].description }}</p>

                    <div class="mt-4 d-flex flex-column">
                      <a :href="projects[2].gitHub" target="_blank" class="btnMobile mt-2">Repo Link</a>
                      <a :href="projects[2].vercel" target="_blank" class="btnMobile mt-3">Hosted Link</a>
                    </div>

                    </template>
                </MobileCard>      
    </div>

     </div>
     <Spinner v-else/>

        </div>

        <!-- Logo -->
      <div class="tab-pane fade" id="pills-logo" role="tabpanel" aria-labelledby="pills-logo-tab">
        <div class="projectsDiv" v-if="projects">

          <!-- Desktop cards -->     
          <card class="cardDkt">
                    <template #cardImg>
                    <img :src="projects[1].img_url" :alt="projects[1].projectName" loading="eager" class="img-fluid card-img-top">
                    </template>
                    <template #cardOverlay>
                    
                    <h5 class="card-title">{{ projects[1].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[1].description }}</p>

                    <div class="mt-4 buttons">
                      <a :href="projects[1].gitHub" target="_blank" class="button btn-outline-card mx-2">Repo Link</a>
                      <a :href="projects[1].vercel" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
                    </div>

                    </template>
            </card>
            
            <card class="cardDkt">
                    <template #cardImg>
                    <img :src="projects[7].img_url" :alt="projects[7].projectName" loading="eager" class="img-fluid card-img-top">
                    </template>
                    <template #cardOverlay>
                    
                    <h5 class="card-title">{{ projects[7].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[7].description }}</p>

                    <div class="mt-4 buttons">
                      <a :href="projects[7].gitHub" target="_blank" class="button btn-outline-card mx-2">Repo Link</a>
                      <a :href="projects[7].vercel" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
                    </div>

                    </template>
            </card>

            <card class="cardDkt">
                    <template #cardImg>
                    <img :src="projects[8].img_url" :alt="projects[8].projectName" loading="eager" class="img-fluid card-img-top">
                    </template>
                    <template #cardOverlay>
                    
                    <h5 class="card-title">{{ projects[8].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[8].description }}</p>

                    <div class="mt-4 buttons">
                      <a :href="projects[8].gitHub" target="_blank" class="button btn-outline-card mx-2">Repo Link</a>
                      <a :href="projects[8].vercel" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
                    </div>

                    </template>
            </card>

        </div>
        <Spinner v-else/>

        <!-- Mobile Card -->
     <div v-if="projects?.length">

      <div class="Mobile">
                <MobileCard class="card mt-4">
                    <template #cardHeader>
                    <img :src="projects[1].mobileImage" :alt="projects[1].projectName" loading="eager" class="img-fluid">
                    </template>
                    <template #cardBody>
                    <h5 class="card-title">{{ projects[1].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[1].description }}</p>

                    <div class="mt-4 d-flex flex-column">
                      <a :href="projects[1].gitHub" target="_blank" class="btnMobile mt-2">Repo Link</a>
                      <a :href="projects[1].vercel" target="_blank" class="btnMobile mt-3">Hosted Link</a>
                    </div>

                    </template>
                </MobileCard>      
    </div>

    <div class="Mobile">
                <MobileCard class="card mt-4">
                    <template #cardHeader>
                    <img :src="projects[7].mobileImage" :alt="projects[7].projectName" loading="eager" class="img-fluid">
                    </template>
                    <template #cardBody>
                    <h5 class="card-title">{{ projects[7].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[7].description }}</p>

                    <div class="mt-4 d-flex flex-column">
                      <a :href="projects[7].gitHub" target="_blank" class="btnMobile mt-2">Repo Link</a>
                      <a :href="projects[7].vercel" target="_blank" class="btnMobile mt-3">Hosted Link</a>
                    </div>

                    </template>
                </MobileCard>      
    </div>

    <div class="Mobile">
                <MobileCard class="card mt-4">
                    <template #cardHeader>
                    <img :src="projects[8].mobileImage" :alt="projects[8].projectName" loading="eager" class="img-fluid">
                    </template>
                    <template #cardBody>
                    <h5 class="card-title">{{ projects[8].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[8].description }}</p>

                    <div class="mt-4 d-flex flex-column">
                      <a :href="projects[8].gitHub" target="_blank" class="btnMobile mt-2">Repo Link</a>
                      <a :href="projects[8].vercel" target="_blank" class="btnMobile mt-3">Hosted Link</a>
                    </div>

                    </template>
                </MobileCard>      
    </div>

     </div>
     <Spinner v-else/>

     </div>

       <!-- Website -->
       <div class="tab-pane fade" id="pills-website" role="tabpanel" aria-labelledby="pills-website-tab">
        <div class="projectsDiv" v-if="projects">

          <!-- Desktop cards -->     
          <card class="cardDkt">
                    <template #cardImg>
                    <img :src="projects[9].img_url" :alt="projects[9].projectName" loading="eager" class="img-fluid card-img-top">
                    </template>
                    <template #cardOverlay>
                    
                    <h5 class="card-title">{{ projects[9].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[9].description }}</p>

                    <div class="mt-4 buttons">
                      <a :href="projects[9].gitHub" target="_blank" class="button btn-outline-card mx-2">Repo Link</a>
                      <a :href="projects[9].vercel" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
                    </div>

                    </template>
            </card>

        </div>
        <Spinner v-else/>

        <!-- Mobile Card -->
     <div v-if="projects?.length">
      <div class="Mobile">
                <MobileCard class="card mt-4">
                    <template #cardHeader>
                    <img :src="projects[9].mobileImage" :alt="projects[9].projectName" loading="eager" class="img-fluid">
                    </template>
                    <template #cardBody>
                    <h5 class="card-title">{{ projects[9].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[9].description }}</p>

                    <div class="mt-4 d-flex flex-column">
                      <a :href="projects[9].gitHub" target="_blank" class="btnMobile mt-2">Repo Link</a>
                      <a :href="projects[9].vercel" target="_blank" class="btnMobile mt-3">Hosted Link</a>
                    </div>

                    </template>
                </MobileCard>      
    </div>
     </div>
     <Spinner v-else/>

       </div>

      <!-- End of tab control -->
    </div>
    
  </div>
</div>
</template>

<script setup>
import Card from './Card.vue'
import MobileCard from './MobileCard.vue'
import { computed, onMounted } from 'vue'
import { useStore } from 'vuex'
    const store = useStore()
    // const allProjects = computed( ()=> store.state.projects)
    // const digit
    const projects = computed(() => store.state.projects )
    
    onMounted(() => {
      setTimeout(()=>{
        store.dispatch('fetchProjects')
      }, 1000)
    })

</script>

<style>

</style>