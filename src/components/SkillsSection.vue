<template>
    <div class="container-fluid">
      <div class="row" data-aos="fade-up"  data-aos-duration="3000">
                  <h2 class="display-3 text-white fadeInUp secHeading mt-4">Skills</h2>
                  <div class=" sectionP" v-if="skills?.length">
                      <div class="skillsText" v-for="skill in skills" :key="skill.id">
                          <h4 class="fw-bold mt-3" v-if="skills">{{  skill.skillName }}<span>{{  skill.level }}</span></h4>
                          
                          <p v-if="skills">{{  skill.description }}</p>
                      </div>
                    
                  </div>
                  <Spinner v-else/>
          </div>
    </div>
  </template>
  
  <script setup>
  import AOS from 'aos';
    import Spinner from './Spinner.vue'
    import { computed, onMounted } from 'vue'
    import { useStore } from 'vuex'
    const store = useStore()
    const skills = computed(() => store.state.skills)
    
    onMounted(() => {
      setTimeout(()=>{
        store.dispatch('fetchSkills')
      }, 1000);
      AOS.init();
    })
  </script>
  
  <style>
  /* Skills section */
#skills{
  height: auto;
  background-color: var(--primary);
  padding-top: 4rem;
}

.skillsText{
  width: 80vw;
  height: auto;
  margin: auto;
  text-align: left;
  background-color: transparent;
}

#skills h4{
  color: var(--alternative);
  margin-bottom: 1rem;
}

#skills span{
  color: var(--secondary);
}

#skills p{
  font-size: 18px;
  color: var(--secondary);
  margin-bottom: 2.2rem;
}

/* Media query */
@media (width < 999px)
{
  /* Skills Section */
#skills{
    height: auto;
    padding-top: 1rem;
}

.skillsText{
    width: 80vw;
    text-align: center;
}

#skills h4{
    font-size: 1.7rem;
}
}
  </style>