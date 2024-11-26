<template>
    <div class="modal fade" id="UiAndUxModal" tabindex="-1" aria-labelledby="UiAndUxModalLabel" aria-hidden="true">
      <div class="modal-dialog modal-dialog-centered modal-dialog-scrollable">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title" id="UiAndUxModalLabel">UI/UX Hackathon Case Study</h5>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
          <div class="modal-body">
            <div class="aws-certificates" v-if="bagdes">
            <div class="certificate-content">
                <img :src="bagdes[3].img_url" :alt="bagdes[3].title" loading="eager" class="img-fluid certificates">
                <a href="https://drive.google.com/file/d/1iH1U8b_F3dTOvqKMYS-7_-QWxPLfR8OV/view?usp=sharing" target="_blank"><button class="btnView">View</button></a>
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
 import { computed, onMounted } from 'vue'
  import { useStore } from 'vuex'
  const store = useStore()
  const bagdes = computed(() => store.state.bagdes)

  onMounted(() => {
    setTimeout(()=>{
      store.dispatch('fetchBagdes')
    }, 1000);
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
  max-width: 18rem;
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