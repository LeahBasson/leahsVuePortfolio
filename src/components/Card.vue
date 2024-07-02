<template>
    <div class="card">

        <slot name="cardImg"></slot>
        
        <div class="card-img-overlay">
            <slot name="cardOverlay"></slot>
        </div>
    
        
    </div>
</template>

<script>
    export default {
         name: 'CardComp'
}
</script>

<style scoped>
   .card {
  border: 0.1rem solid var(--alternative);
  border-radius: 0;
}
</style>