<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <h2 class="display-3 text-white fadeInUp p-3 secHeading">About</h2>
      </div>
    </div>

    <div class="row">
      <div class="aboutSection">

        <div class="aboutImg">
        <img class="img-fluid" src="https://leahbasson.github.io/MyImages/images/aboutImg.jpg" alt="leah" loading="eager">
        </div>

        <div class="aboutText">
          <p  class="text-white sectionP mt-4" v-if="about">
            <span>{{ about[0]}}</span>
          </p>
          <Spinner v-else/>
        </div>

      </div>
    </div>
                
    </div>
  </template>
  
  <script setup>
    import Spinner from './Spinner.vue'
    import { computed, onMounted } from 'vue'
    import { useStore } from 'vuex'
    const store = useStore()
    const about = computed(() => store.state.about)
    onMounted(() => {
      setTimeout(()=>{
        store.dispatch('fetchAbout')
      }, 1000)
    })
  </script>
  
  <style>
  /* About Section */
#about{
  height: auto;
  background-color: var(--primary);
  text-align: center;
  padding-top: 2rem;
  padding-bottom: 10rem;
}

.aboutSection{
  display: flex;
  justify-content: center;
  align-items: center;
}

.aboutImg{
  width: 40vw;
  margin-left: -8rem;
  order: 0;
}

.aboutText{
  margin-top: -1rem;
  order: 1;
}

.fadeInUp{
  animation-name: fadeInUp;
  animation-duration: 5s;
  animation-fill-mode: both;
}

#about p{
  width: 48vw;
  font-size: 20px;
  height: auto;
  margin: auto;
  background-color: transparent;
}

/* Media query */
@media (width < 999px)
{
  /* About Section */
  #about{
      height: auto;
      padding-top: 0;
      padding-bottom: 0;
  }

  .aboutSection{
    display: flex;
    justify-content: center;
    flex-direction: column;
  }

  .aboutImg{
    width: 80vw;
    margin-left: 0;
    order: 1;
    margin-top: 3rem;
  }

  .aboutText{
    margin-top: 0;
    order: 0;
  }

  #about h2{
      margin-top: 1rem;
  }

  #about p{
      width: 80vw;
      height: auto;
      font-size: 1rem;
  }
}
</style>