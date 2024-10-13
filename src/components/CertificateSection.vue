<template>
    <div class="container-fluid">
        <div class="row" id="topSection">
            <h2 class="display-3 text-white secHeading" data-aos="fade-up"  data-aos-duration="2000">Certificates</h2>
        </div>

        <div class="row" id="certificate-listing" v-if="certificateIntro">
            <div class="certificate-view" data-bs-toggle="modal" data-bs-target="#awsModal" data-aos="fade-up"  data-aos-duration="2000">
                <img :src="certificateIntro[0].img_url" :alt="certificateIntro[0].title" loading="eager" class="img-fluid intro-image">
                 <h2>{{  certificateIntro[0].title }}</h2>
            </div>
            <AwsModal />
            <div class="certificate-view" data-bs-toggle="modal" data-bs-target="#LcModal" data-aos="fade-up"  data-aos-duration="2000">
                <img :src="certificateIntro[1].img_url" :alt="certificateIntro[0].title" loading="eager" class="img-fluid lc-image">
                <h2>{{  certificateIntro[1].title }}</h2>
            </div>
            <LcModal />
        </div>
        <Spinner v-else/>
    </div>
</template>

<script setup>
import AOS from 'aos';
import AwsModal from '@/components/AwsModal.vue'
import LcModal from './LcModal.vue';
import Spinner from './Spinner.vue'
  import { computed, onMounted } from 'vue'
  import { useStore } from 'vuex'
  const store = useStore()
  const certificateIntro = computed(() => store.state.certificateIntro)

  onMounted(() => {
    setTimeout(()=>{
      store.dispatch('fetchCertificateIntro')
    }, 1000);
    AOS.init();
  })
</script>

<style>
/* Certificate Section */
#topSection{
    background-color: var(--primary);
    padding-top: 5rem;
}

#certificate-listing{
    display: flex;
    gap: 38rem;
    justify-content: center;
    background-color: var(--primary);
}

#certificate-listing h2{
    color: var(--secondary);
    font-family: "Poppins", sans-serif;
    font-weight: 400;
    padding-top: 2rem;
}

.certificate-view:hover{
    transform: translateY(-10px);
    transition: transform 0.5s ease-in-out;
}

.certificate-view {
    width: 22rem;
    transition: transform 0.5s ease-in-out;
    cursor: pointer;
}

.intro-image{
    width: 14rem;
    margin-top: 3rem;
    border: 1px solid var(--secondary);
}

.lc-image{
    width: 14rem;
    margin-top: 3rem;
    border: 1px solid var(--secondary);
}

/* Media query */
@media (width < 999px)
{
    .certificate-view{
    width: 65%; 
}
.intro-image{
    width: 100%;
}

}
</style>