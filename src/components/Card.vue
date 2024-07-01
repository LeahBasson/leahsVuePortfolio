<template>
    <div class="card">

        <!-- <div class="card-header">
         <slot name="cardHeader"></slot>
        </div>

        <div class="card-body">
          <slot name="cardBody"></slot>
        </div> -->

        
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

<style>
   
</style>