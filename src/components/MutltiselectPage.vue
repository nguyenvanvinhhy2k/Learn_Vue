<template>
  <div class="">
    <h1>MultiSelect</h1>
    <MultiSelect
      :options="days"
      displayProperty="title"
      valueProperty="shortcut"
    />
  </div>
</template>

<script>
import MultiSelect from "../components/Multiselect.vue";
export default {
  name: "VuelidateS",
  components: { MultiSelect },
  data() {
    return {
      days: [
        { title: "Saturday", shortcut: "sat" },
        { title: "Sunday", shortcut: "sun" },
        { title: "Monday", shortcut: "mon" },
      ],
      selectDays: [],
    };
  },
};
</script>

<style scoped></style>
