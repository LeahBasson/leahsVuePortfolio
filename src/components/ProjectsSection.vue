<template>
  <div class="container-fluid projects">

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
          <h5 class="card-title">{{ project.projectName }}</h5>
          <p class="card-text mt-1">{{ project.description }}</p>
          <div class="mt-4 buttons">
            <a :href="project.gitHub" target="_blank" class="button btn-outline-card mx-2">Repo Link</a>
            <a :href="project.hostedLink" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
          </div>

          </template>
      </card>         
              
    </div>
    <Spinner v-else/>

    <!-- Mobile Card -->  
    <div class="Mobile" v-if="projects?.length">
      <MobileCard v-for="project in projects" :key="project.id" class="card mt-4">
          <template #cardHeader>
          <img :src="project.img_url" :alt="project.projectName" loading="eager" class="img-fluid mobileImage">
          </template>

          <template #cardBody>
          <h5 class="card-title">{{ project.projectName }}</h5>
          <p class="card-text mt-1">{{ project.description }}</p>

          <div class="mt-4 d-flex flex-column">
            <a :href="project.gitHub" target="_blank" class="btnMobile mt-2">Repo Link</a>
            <a :href="project.hostedLink" target="_blank" class="btnMobile mt-3">Hosted Link</a>
          </div>
          </template>
      </MobileCard>      
    </div>
    <Spinner v-else/>

   
    </div>  <!--End of all projects-->

      <!-- Digital Artwork -->
      <div class="tab-pane fade" id="pills-artwork" role="tabpanel" aria-labelledby="pills-artwork-tab">

        <div class="projectsDiv" v-if="projects">
            <!-- Desktop cards -->     
            <card class="cardDkt">
                <template #cardImg>
                <img :src="projects[8].img_url" :alt="projects[8].projectName" loading="eager" class="img-fluid card-img-top">
                </template>

                <template #cardOverlay>   
                <h5 class="card-title">{{ projects[8].projectName }}</h5>
                <p class="card-text mt-1">{{ projects[8].description }}</p>
                <div class="mt-4 buttons">
                  <a :href="projects[8].gitHub" target="_blank" class="button btn-outline-card mx-2">Repo Link</a>
                  <a :href="projects[8].hostedLink" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
                </div>
                </template>
            </card> 
                
            <card class="cardDkt">
                <template #cardImg>
                <img :src="projects[4].img_url" :alt="projects[4].projectName" loading="eager" class="img-fluid card-img-top">
                </template>

                <template #cardOverlay>     
                <h5 class="card-title">{{ projects[4].projectName }}</h5>
                <p class="card-text mt-1">{{ projects[4].description }}</p>
                <div class="mt-4 buttons">
                  <a :href="projects[4].gitHub" target="_blank" class="button btn-outline-card mx-2">Repo Link</a>
                  <a :href="projects[4].hostedLink" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
                </div>
                </template>
            </card>  

            <card class="cardDkt">
                <template #cardImg>
                <img :src="projects[6].img_url" :alt="projects[6].projectName" loading="eager" class="img-fluid card-img-top">
                </template>
                
                <template #cardOverlay>    
                <h5 class="card-title">{{ projects[6].projectName }}</h5>
                <p class="card-text mt-1">{{ projects[6].description }}</p>

                <div class="mt-4 buttons">
                  <a :href="projects[6].gitHub" target="_blank" class="button btn-outline-card mx-2">Repo Link</a>
                  <a :href="projects[6].hostedLink" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
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
            <img :src="projects[8].img_url" :alt="projects[8].projectName" loading="eager" class="img-fluid mobileImage">
            </template>

            <template #cardBody>
            <h5 class="card-title">{{ projects[8].projectName }}</h5>
            <p class="card-text mt-1">{{ projects[8].description }}</p>

            <div class="mt-4 d-flex flex-column">
              <a :href="projects[8].gitHub" target="_blank" class="btnMobile mt-2">Repo Link</a>
              <a :href="projects[8].hostedLink" target="_blank" class="btnMobile mt-3">Hosted Link</a>
            </div>
            </template>
        </MobileCard>      
    </div>

    <div class="Mobile">
      <MobileCard class="card mt-4">
          <template #cardHeader>
          <img :src="projects[4].img_url" :alt="projects[4].projectName" loading="eager" class="img-fluid mobileImage">
          </template>

          <template #cardBody>
          <h5 class="card-title">{{ projects[4].projectName }}</h5>
          <p class="card-text mt-1">{{ projects[4].description }}</p>

          <div class="mt-4 d-flex flex-column">
            <a :href="projects[4].gitHub" target="_blank" class="btnMobile mt-2">Repo Link</a>
            <a :href="projects[4].hostedLink" target="_blank" class="btnMobile mt-3">Hosted Link</a>
          </div>
          </template>
      </MobileCard>      
    </div>

    <div class="Mobile">
      <MobileCard class="card mt-4">
          <template #cardHeader>
          <img :src="projects[6].img_url" :alt="projects[6].projectName" loading="eager" class="img-fluid mobileImage">
          </template>
          
          <template #cardBody>
          <h5 class="card-title">{{ projects[6].projectName }}</h5>
          <p class="card-text mt-1">{{ projects[6].description }}</p>

          <div class="mt-4 d-flex flex-column">
            <a :href="projects[6].gitHub" target="_blank" class="btnMobile mt-2">Repo Link</a>
            <a :href="projects[6].hostedLink" target="_blank" class="btnMobile mt-3">Hosted Link</a>
          </div>
          </template>
      </MobileCard>      
    </div>

    </div>
    <Spinner v-else/>

      </div> <!-- End of Digital Artwork -->

        <!-- Mini Project -->
      <div class="tab-pane fade" id="pills-mini-project" role="tabpanel" aria-labelledby="pills-mini-project-tab">
        <div class="projectsDiv" v-if="projects">

          <!-- Desktop cards -->     
          <card class="cardDkt">
            <template #cardImg>
            <img :src="projects[5].img_url" :alt="projects[5].projectName" loading="eager" class="img-fluid card-img-top">
            </template>

            <template #cardOverlay>         
            <h5 class="card-title">{{ projects[5].projectName }}</h5>
            <p class="card-text mt-1">{{ projects[5].description }}</p>

            <div class="mt-4 buttons">
              <a :href="projects[5].gitHub" target="_blank" class="button btn-outline-card mx-2">Repo Link</a>
              <a :href="projects[5].hostedLink" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
            </div>
            </template>
          </card> 

          <card class="cardDkt">
            <template #cardImg>
            <img :src="projects[7].img_url" :alt="projects[7].projectName" loading="eager" class="img-fluid card-img-top">
            </template>

            <template #cardOverlay>        
            <h5 class="card-title">{{ projects[7].projectName }}</h5>
            <p class="card-text mt-1">{{ projects[7].description }}</p>

            <div class="mt-4 buttons">
              <a :href="projects[7].gitHub" target="_blank" class="button btn-outline-card mx-2">Repo Link</a>
              <a :href="projects[7].hostedLink" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
            </div>
            </template>
          </card> 

          <card class="cardDkt">
            <template #cardImg>
            <img :src="projects[11].img_url" :alt="projects[11].projectName" loading="eager" class="img-fluid card-img-top">
            </template>

            <template #cardOverlay>     
            <h5 class="card-title">{{ projects[11].projectName }}</h5>
            <p class="card-text mt-1">{{ projects[11].description }}</p>

            <div class="mt-4 buttons">
              <a :href="projects[11].gitHub" target="_blank" class="button btn-outline-card mx-2">Repo Link</a>
              <a :href="projects[11].hostedLink" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
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
                    <img :src="projects[5].img_url" :alt="projects[5].projectName" loading="eager" class="img-fluid mobileImage">
                    </template>
                    <template #cardBody>
                    <h5 class="card-title">{{ projects[5].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[5].description }}</p>

                    <div class="mt-4 d-flex flex-column">
                      <a :href="projects[5].gitHub" target="_blank" class="btnMobile mt-2">Repo Link</a>
                      <a :href="projects[5].hostedLink" target="_blank" class="btnMobile mt-3">Hosted Link</a>
                    </div>

                    </template>
                </MobileCard>      
    </div>

    <div class="Mobile">
                <MobileCard class="card mt-4">
                    <template #cardHeader>
                    <img :src="projects[7].img_url" :alt="projects[7].projectName" loading="eager" class="img-fluid mobileImage">
                    </template>
                    <template #cardBody>
                    <h5 class="card-title">{{ projects[7].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[7].description }}</p>

                    <div class="mt-4 d-flex flex-column">
                      <a :href="projects[7].gitHub" target="_blank" class="btnMobile mt-2">Repo Link</a>
                      <a :href="projects[7].hostedLink" target="_blank" class="btnMobile mt-3">Hosted Link</a>
                    </div>

                    </template>
                </MobileCard>      
    </div>

    <div class="Mobile">
                <MobileCard class="card mt-4">
                    <template #cardHeader>
                    <img :src="projects[11].img_url" :alt="projects[11].projectName" loading="eager" class="img-fluid mobileImage">
                    </template>
                    <template #cardBody>
                    <h5 class="card-title">{{ projects[11].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[11].description }}</p>

                    <div class="mt-4 d-flex flex-column">
                      <a :href="projects[11].gitHub" target="_blank" class="btnMobile mt-2">Repo Link</a>
                      <a :href="projects[11].hostedLink" target="_blank" class="btnMobile mt-3">Hosted Link</a>
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
                    <img :src="projects[3].img_url" :alt="projects[3].projectName" loading="eager" class="img-fluid card-img-top">
                    </template>
                    <template #cardOverlay>
                    
                    <h5 class="card-title">{{ projects[3].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[3].description }}</p>

                    <div class="mt-4 buttons">
                      <a :href="projects[3].gitHub" target="_blank" class="button btn-outline-card mx-2">Repo Link</a>
                      <a :href="projects[3].hostedLink" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
                    </div>

                    </template>
            </card>
            
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
                      <a :href="projects[9].hostedLink" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
                    </div>

                    </template>
            </card>

            <card class="cardDkt">
                    <template #cardImg>
                    <img :src="projects[10].img_url" :alt="projects[10].projectName" loading="eager" class="img-fluid card-img-top">
                    </template>
                    <template #cardOverlay>
                    
                    <h5 class="card-title">{{ projects[10].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[10].description }}</p>

                    <div class="mt-4 buttons">
                      <a :href="projects[10].gitHub" target="_blank" class="button btn-outline-card mx-2">Repo Link</a>
                      <a :href="projects[10].hostedLink" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
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
                    <img :src="projects[3].img_url" :alt="projects[3].projectName" loading="eager" class="img-fluid mobileImage">
                    </template>
                    <template #cardBody>
                    <h5 class="card-title">{{ projects[3].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[3].description }}</p>

                    <div class="mt-4 d-flex flex-column">
                      <a :href="projects[3].gitHub" target="_blank" class="btnMobile mt-2">Repo Link</a>
                      <a :href="projects[3].hostedLink" target="_blank" class="btnMobile mt-3">Hosted Link</a>
                    </div>

                    </template>
                </MobileCard>      
    </div>

    <div class="Mobile">
                <MobileCard class="card mt-4">
                    <template #cardHeader>
                    <img :src="projects[7].img_url" :alt="projects[7].projectName" loading="eager" class="img-fluid mobileImage">
                    </template>
                    <template #cardBody>
                    <h5 class="card-title">{{ projects[7].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[7].description }}</p>

                    <div class="mt-4 d-flex flex-column">
                      <a :href="projects[7].gitHub" target="_blank" class="btnMobile mt-2">Repo Link</a>
                      <a :href="projects[7].hostedLink" target="_blank" class="btnMobile mt-3">Hosted Link</a>
                    </div>

                    </template>
                </MobileCard>      
    </div>

    <div class="Mobile">
                <MobileCard class="card mt-4">
                    <template #cardHeader>
                    <img :src="projects[8].img_url" :alt="projects[8].projectName" loading="eager" class="img-fluid mobileImage">
                    </template>
                    <template #cardBody>
                    <h5 class="card-title">{{ projects[8].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[8].description }}</p>

                    <div class="mt-4 d-flex flex-column">
                      <a :href="projects[8].gitHub" target="_blank" class="btnMobile mt-2">Repo Link</a>
                      <a :href="projects[8].hostedLink" target="_blank" class="btnMobile mt-3">Hosted Link</a>
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
                    <img :src="projects[0].img_url" :alt="projects[0].projectName" loading="eager" class="img-fluid card-img-top">
                    </template>
                    <template #cardOverlay>
                    
                    <h5 class="card-title">{{ projects[0].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[0].description }}</p>

                    <div class="mt-4 buttons">
                      <a :href="projects[0].gitHub" target="_blank" class="button btn-outline-card mx-2">Repo Link</a>
                      <a :href="projects[0].hostedLink" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
                    </div>

                    </template>
            </card>

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
                      <a :href="projects[1].hostedLink" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
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
                      <a :href="projects[2].hostedLink" target="_blank" class="button btn-outline-card mx-2">Hosted Link</a>
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
                    <img :src="projects[9].img_url" :alt="projects[9].projectName" loading="eager" class="img-fluid mobileImage">
                    </template>
                    <template #cardBody>
                    <h5 class="card-title">{{ projects[9].projectName }}
                    </h5>
                    <p class="card-text mt-1">{{ projects[9].description }}</p>

                    <div class="mt-4 d-flex flex-column">
                      <a :href="projects[9].gitHub" target="_blank" class="btnMobile mt-2">Repo Link</a>
                      <a :href="projects[9].hostedLink" target="_blank" class="btnMobile mt-3">Hosted Link</a>
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
/* Projects Section */
.projects{
  height: auto;
  background-color: var(--primary);
  font-family: "Montserrat", sans-serif;
  color: var(--primary);
  padding-bottom: 4rem;
}

.projects ul{
  background-color: var(--primary);
  width: 80%;
  margin: auto;
  font-family: "Roboto", sans-serif;
  border: 2px solid var(--alternative);
}

.projects li{
  font-size: 1.3rem;
  padding: 8px 32px;
}

:is(.red .nav-link.active,
.red .nav-link.active:hover) {
    background-color: var(--alternative);
}

/* Card  */
.cardDkt {
  width: 47.2%;
  position: relative;
  color: var(--secondary);
  box-shadow: #000 0px 11px 15px 0px; 
  margin-top: 1.4rem;
  margin: 1rem;
}

.cardDkt .card-img-top {
  /* display: block; */
  width: 100%;
  height: 45vh;
  aspect-ratio: 16/9;
  object-position: center;
}

.cardDkt .card-img-overlay {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: absolute;
  bottom: 0; /* Change this to 0 to hide the overlay initially */
  top: 0;
  left: 0;
  right: 0;
  background-color: var(--primary);
  overflow: hidden;
  width: 100%;
  height: 0;
  transition: .5s ease;
  opacity: 0;
}

.cardDkt:hover .card-img-overlay {
  bottom: 100%; /* Show the overlay on hover */
  height: 100%;
  opacity: 1;
}

.projectsDiv .cardDkt h5{
  color: var(--secondary);
  font-size: 1.8rem;
  font-weight: bold;
}

.cardDkt .card-text{
  color: var(--secondary)
}

.cardDkt .button {
  padding: 0.7rem 1.6rem;
  text-decoration: none;
  border-radius: 0.5rem;
}

.cardDkt .btn-outline-card{
  border: 2px solid var(--alternative);
  color: var(--secondary);
}

.cardDkt .btn-outline-card:hover{
  background-color: var(--alternative);
  border: 2px solid var(--secondary);
  color: var(--secondary)
}

.Mobile{
  display: none;
}

.OneCard{
  width: 40vw;
  height: auto;
  margin-left: 9rem;
 
}

.projectsDiv{
  width: 82vw;
  display: flex;
  flex-wrap: wrap;
  margin: auto;
  background-color: transparent;
  margin-left: 8rem;
}

/* Media query */
@media (width < 999px)
{
  /* Projects Section */
.projectsDiv .cardDkt{
  display: none;
}

.Mobile{
  display: block;
}

.mobileImage{
  width: 80rem;
  aspect-ratio: 16/9;
  object-position: center;
  border-bottom: 1px solid var(--alternative);;
}

.projects{
  background-color: var(--primary);
  height: auto;
}
.Mobile h5{
  font-weight: bolder;
}

.Mobile h5 , p{
  color: var(--secondary);
}

.buttons{
  display: none;
}

.btnMobile{
  color: var(--secondary);
  border: 0.1rem solid var(--alternative);
  text-decoration: none;
  border-radius: 0.4rem;
  padding: 0.3rem;
}

.btnMobile:hover{
  background-color: var(--alternative);
  border: 2px solid var(--secondary);
  color: var(--secondary)
}

.projects ul{
  width: 76%;
}

.projects li{
  padding: 8px 1px;
  font-size: 1.2rem;
}

.projectsDiv{
  display: none;
}

.Mobile{
  margin-top: 2rem;
}

.Mobile .card {
  border: 1px solid var(--alternative);
  background-color: transparent;
  width: 80%;
  margin: auto;
  border-radius: 0;
  padding: 0;
}

}
</style>