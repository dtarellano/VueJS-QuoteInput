<template>
   <div class="row">
      <div class="col-md-3 quote" v-for="(quote, index) in quotes">
            <div class="panel panel-default text-center fadeInDown" v-bind:class="{ fadeOutUp: fadeOut }">
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
   data() {
      return {
         fadeOut: false
      };
   },
   methods: {
      remove(index) {
         this.fadeOut = true;
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
@-webkit-keyframes fadeInDown {
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


.fadeOutUp {
   -webkit-animation-name: fadeOutUp;
   animation-name: fadeOutUp;
   -webkit-animation-duration: 1s;
   animation-duration: 1s;
   -webkit-animation-fill-mode: both;
   animation-fill-mode: both;
}
@-webkit-keyframes fadeOutUp {
   0% {
      opacity: 1;
   }
   100% {
      opacity: 0;
      -webkit-transform: translate3d(0, -100%, 0);
      transform: translate3d(0, -100%, 0);
   }
}
@keyframes fadeOutUp {
   0% {
      opacity: 1;
   }
   100% {
      opacity: 0;
      -webkit-transform: translate3d(0, -100%, 0);
      transform: translate3d(0, -100%, 0);
   }
}
</style>
