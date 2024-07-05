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
/* Resume Section*/
#resume{
  height: auto;
  background-color: var(--primary);
  text-align: center;
}

.resText{
  height: auto;
  background-color: transparent;
  margin-left: 11rem;
  text-align: left;
}

.resCenter{
  display: flex;
}

.laptop-container{
  margin-top: 7rem;
  margin-left: 3rem;
}

.laptop {
  animation: bounce 2s infinite;
}

@keyframes bounce {
  0%, 100% {
      transform: translateY(0);
  }
  50% {
      transform: translateY(-30px);
  }
}

.centerBtn{
  text-align: center;
  font-family: "Montserrat", sans-serif;
  margin-top: 1rem;
}

#resume h4{
margin-top: 2rem;
color: var(--alternative); 
}

#resume p{
  color: var(--secondary);
  font-size: 20px;
}

.btnResume{
  background-color: transparent;
  border: 2px solid var(--alternative);
  color: var(--secondary);
  padding: 8px 30px;
  font-size: 18px;
}

.btnResume:hover{
  background-color: var(--alternative);
  border: 2px solid var(--secondary);
}

.btnResume a{
  text-decoration: none;
  color: var(--secondary);
}

/* Media query */
@media (width < 999px)
{
   /* Resume Section */
   #resume{
    height: auto;
}

.resCenter{
  width: 72vw;
  margin: auto;
}

.centerBtn{
  margin-top: 1rem;
}

.resText{
  text-align: center;
  margin-left: 0;
}

#resume h2{
    margin-top: 3rem;
}

#resume h4{
    font-size: 1rem;
}

#resume p{
    font-size: 1rem;
}

.btnResume{
    margin-top: 0;
    font-size: 1rem;
    padding: 5px 32px;
    margin-bottom: 1rem ;
}

.laptop-container{
  display: none;
}
}
</style>