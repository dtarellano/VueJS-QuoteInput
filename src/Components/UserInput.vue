<template>
   <div class="row">
      <div class="col-md-6 col-md-offset-3">
         <textarea v-model="userInput" v-on:keyup="onEnter" class="form-control" rows="3"></textarea>
      </div>
   </div>
</template>

<script>
export default {
   props: ["bar"],
   data() {
      return {
         userInput: ""
      };
   },
   methods: {
      onEnter(event) {
         if (event.key === "Enter") {
            this.$emit("addQuote", this.userInput);
            this.userInput = "";
         }
      }
   }
};
</script>

<style>
</style>
