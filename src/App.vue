<template>
   <div class="container">
      <h2 class="text-center">Le Quotes</h2>
      <div class="progress">
         <div class="progress-bar bar-cap" :style="quoteCapacity">
            <div>
               {{ bar }} / 10
            </div>
         </div>
      </div>
      <div class="row">
         <div class="col-md-6 col-md-offset-3">
            <textarea v-model="userInput" v-on:keyup="onEnter" class="form-control" rows="3"></textarea>
         </div>
      </div>
      <hr>
      <div class="row">
         <div class="col-md-3 col-md-offset-1 quote" v-for="quote in quotes">
            {{ quote }}
         </div>
      </div>

   </div>
</template>

<script>
export default {
   data() {
      return {
         bar: 0,
         userInput: "",
         quotes: []
      };
   },
   methods: {
      onEnter(event) {
         if (event.key === "Enter") {
            if (this.bar >= 10) {
               alert("You Cannot Exceed more than 10 Quotes");
               this.bar = 10;
               this.userInput = "";
               return;
            }
            this.quotes.push(this.userInput.replace(/\n/g, ""));
            this.userInput = "";
            this.bar += 1;
         }
      }
   },
   computed: {
      quoteCapacity() {
         return { width: this.bar + "0%" };
      }
   }
};
</script>

<style scoped>
   .bar-cap {
      width: 100%
   }
   .quote {
   }
</style>
