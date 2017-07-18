<template>
   <div class="container">
      <h2 class="text-center">Le Quotes</h2>
      <app-bar :bar="bar"/>
      <app-input :bar="bar" @addQuote="pushQuote"/>
      <hr>
      <app-quotes :quotes="quotes" @removeQuote="deleteQuote"/>
   </div>
</template>

<script>
import ProgressBar from "./Components/ProgressBar.vue";
import UserInput from "./Components/UserInput.vue";
import Quotes from "./Components/Quotes.vue";

export default {
   data() {
      return {
         bar: 0,
         quotes: []
      };
   },
   methods: {
      pushQuote(input) {
         if (this.bar >= 10) {
            alert("You Cannot Exceed more than 10 Quotes");
            this.bar = 10;
            return;
         }
         this.quotes.push(input);
         this.bar += 1;
      },
      deleteQuote(index) {
         this.quotes.splice(index, 1);
         this.bar -= 1;
      }
   },
   components: {
      "app-bar": ProgressBar,
      "app-input": UserInput,
      "app-quotes": Quotes
   }
};
</script>

<style scoped>
</style>
