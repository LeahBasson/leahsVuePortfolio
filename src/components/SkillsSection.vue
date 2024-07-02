<template>
    <div class="container-fluid">
      <div class="row">
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
    import Spinner from './Spinner.vue'
    import { computed, onMounted } from 'vue'
    import { useStore } from 'vuex'
    const store = useStore()
    const skills = computed(() => store.state.skills)
    
    onMounted(() => {
      setTimeout(()=>{
        store.dispatch('fetchSkills')
      }, 1000)
    })
  </script>
  
  <style>
  
  </style>