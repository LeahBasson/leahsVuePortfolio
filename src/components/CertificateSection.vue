<template>
    <div class="container-fluid">
        <div class="row" id="topSection">
            <h2 class="display-3 text-white secHeading">Certificates</h2>
        </div>

        <div class="row" id="certificate-listing">
            <div class="certificate-view" data-bs-toggle="modal" data-bs-target="#awsModal" v-if="certificateIntro">
                <img :src="certificateIntro[0].img_url" :alt="certificateIntro[0].title" loading="eager" class="img-fluid">
                <!-- <img class="img-fluid" src="https://leahbasson.github.io/MyImages/images/aws_image.jpg" loading="eager" alt="aws_image"> -->
                <h2>AWS</h2>
            </div>
            <Spinner v-else/>
            <AwsModal />
            <div class="certificate-view">
                <img class="img-fluid" src="https://leahbasson.github.io/MyImages/images/lifechoices_image.jpg" loading="eager" alt="aws_image">
                <h2>Life Choices Academy</h2>
            </div>
        </div>
    </div>
</template>

<script setup>
import AOS from 'aos';
import AwsModal from '@/components/AwsModal.vue'
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
    gap: 2rem;
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

img[alt="aws_image"]{
    width: 14rem;
    margin-top: 3rem;
    box-shadow: 0.2rem 0.2rem 1rem 0.2rem var(--secondary);
}
</style>