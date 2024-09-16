<template>
   <div>
    <section class="row" id="home">
      <LandingSection/>
    </section>
    <section class="row" id="about">
      <AboutSection/>
    </section>
    <section class="row" id="skills">
      <SkillsSection/>
    </section>
    <section class="row" id="resume">
      <ResumeSection/>
    </section>
    <section class="row" id="projects">
      <ProjectsSection/>
    </section>
    <!-- <section class="row" id="testimonials">
      <TestimonialSection/>
    </section> -->
    <section class="row" id="reachMe">
      <ReachMeSection/>
    </section>
  </div>  
</template>

<script>
import LandingSection from '@/components/LandingSection.vue';
import AboutSection from '@/components/AboutSection.vue';
import ResumeSection from '@/components/ResumeSection.vue';
import SkillsSection from '@/components/SkillsSection.vue';
import ProjectsSection from '@/components/ProjectsSection.vue';
// import TestimonialSection from '@/components/TestimonialSection.vue';
import ReachMeSection from '@/components/ReachMeSection.vue';

 export default {
  name: 'HomeView',

  components: {
   LandingSection,
   AboutSection,
   ResumeSection,
   SkillsSection,
   ProjectsSection,
  //  TestimonialSection,
   ReachMeSection
  }
  
}
</script>
