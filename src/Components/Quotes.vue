<template>
   <div class="row">
      <div class="col-md-3 quote" v-for="(quote, index) in quotes">
            <div class="panel panel-default text-center fadeInDown">
               <div class="panel-body" @click="remove(index)">
                  {{ quote }}
               </div>
            </div>
      </div>
   </div>
</template>

<script>
export default {
   props: ["quotes"],
   methods: {
      remove(index) {
         this.$emit("removeQuote", index);
      }
   }
};
</script>

<style scoped>
.fadeInDown {
   -webkit-animation-name: fadeInDown;
   animation-name: fadeInDown;
   -webkit-animation-duration: 1s;
   animation-duration: 1s;
   -webkit-animation-fill-mode: both;
   animation-fill-mode: both;
   }
@keyframes fadeInDown {
   0% {
      opacity: 0;
      -webkit-transform: translate3d(0, -100%, 0);
      transform: translate3d(0, -100%, 0);
   }
   100% {
      opacity: 1;
      -webkit-transform: none;
      transform: none;
   }
}
</style>
