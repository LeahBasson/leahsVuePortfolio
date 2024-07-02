<template>
    <div class="MobileCard">

        <div class="card-header">
         <slot name="cardHeader"></slot>
        </div>

        <div class="card-body">
          <slot name="cardBody"></slot>
        </div>
        
    </div>
</template>

<script>
    export default {
         name: 'MobileCardComp'
}
</script>

<style scoped>
.card-header{
  padding: 0;
}
</style>