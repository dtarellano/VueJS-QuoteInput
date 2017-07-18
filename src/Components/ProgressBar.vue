<template>
   <div class="progress">
      <div class="progress-bar bar-cap" :style="quoteCapacity">
         <div>
            {{ bar }} / 10
         </div>
      </div>
   </div>
</template>

<script>
export default {
   props: ["bar"],
   computed: {
      quoteCapacity() {
         return { width: this.bar + "0%" };
      }
   }
};
</script>

<style>
</style>
