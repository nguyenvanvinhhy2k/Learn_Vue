<template>
  <div id="app" class="container mt-10">
    <!-- <LearnVue msg="hello" /> -->
    <!-- <VeeValidateForm /> -->
    <!-- VuelidateForm -->
    <Vuelidate />
  </div>
</template>

<script>
// import LearnVue from "./components/LearnVue.vue";
// import VeeValidateForm from "./components/VeeValidateForm.vue";
import Vuelidate from "./components/MutltiselectPage.vue";

export default {
  components: {
    // LearnVue,
    Vuelidate,
    // VuelidateForm,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  
}
@import "~bootstrap/dist/css/bootstrap.css";
</style>
