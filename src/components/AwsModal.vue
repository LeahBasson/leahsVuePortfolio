<template>
    <div class="modal fade" id="awsModal" tabindex="-1" aria-labelledby="awsModalLabel" aria-hidden="true">
      <div class="modal-dialog modal-dialog-centered modal-dialog-scrollable">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title" id="awsModalLabel">AWS Certificates</h5>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
          <div class="modal-body">
            <h4>Introduction</h4>
            <div class="aws-certificates" v-if="certificates">
                <div class="certificate-content">
                  <img :src="certificates[0].img_url" :alt="certificates[0].certificate" loading="eager" class="img-fluid certificates">
                  <p>{{ certificates[0].certificate }}</p>
                  <a href="https://leahbasson.github.io/IntroToAws/" target="_blank"><button class="btnView">View</button></a>
            </div>
            <div class="certificate-content">
              <img :src="certificates[1].img_url" :alt="certificates[1].certificate" loading="eager" class="img-fluid certificates">
                  <p>{{ certificates[1].certificate }}</p>
                  <a href="https://leahbasson.github.io/BuildingACloudCareer/" target="_blank"><button class="btnView">View</button></a>
            </div>
            <div class="certificate-content">
              <img :src="certificates[2].img_url" :alt="certificates[2].certificate" loading="eager" class="img-fluid certificates">
                  <p>{{ certificates[2].certificate }}</p>
                  <a href="https://leahbasson.github.io/DemistifyingGenAi/" target="_blank"><button class="btnView">View</button></a>
            </div>
            <div class="certificate-content">
              <img :src="certificates[3].img_url" :alt="certificates[3].certificate" loading="eager" class="img-fluid certificates">
                  <p>{{ certificates[3].certificate }}</p>
                  <a href="https://leahbasson.github.io/JobRolesInTheCloud/" target="_blank"><button class="btnView">View</button></a>
            </div>
            <div class="certificate-content">
              <img :src="certificates[4].img_url" :alt="certificates[4].certificate" loading="eager" class="img-fluid certificates">
                  <p>{{ certificates[4].certificate }}</p>
                  <a href="https://leahbasson.github.io/WhyGetAwsCertified/" target="_blank"><button class="btnView">View</button></a>
            </div>
            </div>
            <Spinner v-else/>
            <h4 class="heading">Computer Foundations</h4>
            <div class="aws-certificates" v-if="certificates">
                <div class="certificate-content">
                  <img :src="certificates[5].img_url" :alt="certificates[5].certificate" loading="eager" class="img-fluid certificates">
                  <p>{{ certificates[5].certificate }}</p>
                  <a href="https://leahbasson.github.io/CF1/" target="_blank"><button class="btnView">View</button></a>
            </div>
            <div class="certificate-content">
              <img :src="certificates[6].img_url" :alt="certificates[6].certificate" loading="eager" class="img-fluid certificates">
                  <p>{{ certificates[6].certificate }}</p>
                  <a href="https://leahbasson.github.io/CF2/" target="_blank"><button class="btnView">View</button></a>
            </div>
            <div class="certificate-content">
              <img :src="certificates[7].img_url" :alt="certificates[7].certificate" loading="eager" class="img-fluid certificates">
                  <p>{{ certificates[7].certificate }}</p>
                  <a href="https://leahbasson.github.io/CF3/" target="_blank"><button class="btnView">View</button></a>
            </div>
            <div class="certificate-content">
              <img :src="certificates[8].img_url" :alt="certificates[8].certificate" loading="eager" class="img-fluid certificats">
                  <p>{{ certificates[8].certificate }}</p>
                  <a href="https://leahbasson.github.io/CF4/" target="_blank"><button class="btnView">View</button></a>
            </div>
            </div>
            <Spinner v-else/>
            <h4 class="heading">Becoming a Cloud Practitioner</h4>
            <div class="aws-certificates" v-if="certificates">
                <div class="certificate-content">
                  <img :src="certificates[9].img_url" :alt="certificates[9].certificate" loading="eager" class="img-fluid certificates">
                  <p>{{ certificates[9].certificate }}</p>
                  <a href="https://leahbasson.github.io/BCP1/" target="_blank"><button class="btnView">View</button></a>
            </div>
            <div class="certificate-content">
              <img :src="certificates[10].img_url" :alt="certificates[10].certificate" loading="eager" class="img-fluid certificates">
                  <p>{{ certificates[10].certificate }}</p>
                  <a href="https://leahbasson.github.io/BCP2/" target="_blank"><button class="btnView">View</button></a>
            </div>
            <div class="certificate-content">
              <img :src="certificates[11].img_url" :alt="certificates[11].certificate" loading="eager" class="img-fluid certificates">
                  <p>{{ certificates[11].certificate }}</p>
                  <a href="https://leahbasson.github.io/BCP3/" target="_blank"><button class="btnView">View</button></a>
            </div>
            <div class="certificate-content">
              <img :src="certificates[12].img_url" :alt="certificates[12].certificate" loading="eager" class="img-fluid certificats">
                  <p>{{ certificates[12].certificate }}</p>
                  <a href="https://leahbasson.github.io/BCP4/" target="_blank"><button class="btnView">View</button></a>
            </div>
            <div class="certificate-content">
              <img :src="certificates[13].img_url" :alt="certificates[13].certificate" loading="eager" class="img-fluid certificats">
                  <p>{{ certificates[13].certificate }}</p>
                  <a href="https://leahbasson.github.io/BCPLab/" target="_blank"><button class="btnView">View</button></a> 
            </div>
            </div>
            <Spinner v-else/>
            <h4 class="heading">Exam Prep</h4>
            <div class="aws-certificates" v-if="certificates">
                <div class="certificate-content">
                  <img :src="certificates[14].img_url" :alt="certificates[14].certificate" loading="eager" class="img-fluid certificates">
                  <p>{{ certificates[14].certificate }}</p>
                  <a href="https://leahbasson.github.io/ExamPrep/" target="_blank"><button class="btnView">View</button></a>
            </div>
            </div>
            <Spinner v-else/>
          </div>
          <div class="modal-footer">
            <button type="button" class="btnClose" data-bs-dismiss="modal">Close</button>
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
  const certificates = computed(() => store.state.certificates)

  onMounted(() => {
    setTimeout(()=>{
      store.dispatch('fetchCertificates')
    }, 1000)
  })
</script>

<style>
.aws-certificates{
    display: flex;
    justify-content: center;
    gap: 0.9rem;
    flex-wrap: wrap;
}

.modal-title{
    color: var(--primary);
    font-family: "Poppins", sans-serif;
}

.modal-body h4{
    color: var(--primary);
    font-family: "Poppins", sans-serif;
    text-align: center;
    text-shadow: 1px 1px red;
}

.certificates{
  width: 100%;
}

.certificate{
  width: 58%;
}

.certificate-content {
  /* flex: 1 1 30%; */
  max-width: 16rem;
  padding: center;
}

.modal{
  background-color: var(--primary);
}

.certificate-content p{
  color: var(--primary);
  font-family: "Poppins", sans-serif;
}

.btnView{
  background-color: var(--alternative);
  color: var(--secondary);
  padding: 0.5rem 2rem;
  border: none;
  border-radius: 0.3rem;
}

.btnView:hover{
  background-color: rgb(255, 40, 40);
}

.btnClose{
  color: var(--primary);
  padding: 0.5rem 2rem;
  border: 1px solid var(--alternative);
  border-radius: 0.3rem;
  background-color: var(--secondary);
}

.btnClose:hover{
  background-color: var(--alternative);
  color: var(--secondary);
  transition: all 1s;
}
.heading{
  margin-top: 2rem;
}

.p-button{
  margin-top: 3rem;
}

p-btm{
  padding-bottom: 3rem;
}

/* Media query */
@media (width < 999px)
{
  .btnClose{
    margin: auto;
  }
}
</style>