<template>
    <div class="container-fluid">
        <div class="row">
            <div class=".col-lg-12">
              <h2 class="display-3 text-white fadeInUp secHeading">Resume</h2>
              </div>     
        </div>
        <div class="row" v-if="resume?.length">

          <div class="col-lg-12 resCenter">

            <div>
            <div class="sectionP resText" v-for="resume in resume" :key="resume.id">
        
        <h4 class="fw-bold" v-if="resume">
            <span>{{ resume.certificate}}</span>
        </h4>
          
        <p class="fw-bold" v-if="resume">
            <span>{{ resume.place }}</span>
        </p>
       
      </div>

      <div class="sectionP resText">
        <h4 class="fw-bold" v-if="subjects">
            {{ subjects[0].title}}
            <p class="mt-3">{{ subjects[0].subject1 }}</p>
            <p>{{ subjects[0].subject2 }}</p>
            <p>{{ subjects[0].subject3 }}</p>
        </h4>
       
        </div>

      </div>

      <div class="laptop-container">
        <img class="img-fluid laptop" src="https://leahbasson.github.io/MyImages/images/laptopPng2.png" loading="eager">
      </div>
      
            
          </div>
          
        </div> 
        <Spinner v-else/>

        <div class="row">
          <div class="centerBtn">
                  <button class="btnResume mt-2"><a  href="https://drive.google.com/uc?export=download&id=1hlzWUU4luPbO_ptpqSxozBAJK0YiVQn3" id="download-link">Download my CV</a></button>
          </div>
        </div>
        
    </div>
</template>

<script setup>
  import Spinner from './Spinner.vue'
  import { computed, onMounted } from 'vue'
  import { useStore } from 'vuex'
  const store = useStore()
  const resume = computed(() => store.state.resume)
  const subjects = computed(() => store.state.subjects)
  
  onMounted(() => {
    setTimeout(()=>{
      store.dispatch('fetchResume'),
      store.dispatch('fetchSubject')
    }, 1000)
  })
</script>

<style>

</style>