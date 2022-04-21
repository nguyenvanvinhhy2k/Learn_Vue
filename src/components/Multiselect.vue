<template>
  <div class="">
    <div class="container" @click="handleClick" @blur="focused = false">
      Chọn ngày đẹp...
      <div
        class="content"
        v-show="focused"
        v-for="(option, i) in options"
        :key="i"
      >
        <div class="content_checkbox"></div>
        <div class="content_text">{{ option[displayProperty] }}</div>

        <p></p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MultiSelect",
  data() {
    return {
      focused: false,
    };
  },
  methods: {
    handleClick() {
      this.focused = !this.focused;
    },
  },
  props: {
    options: {
      type: Array,
      default: () => [],
    },
    value: {
      default: () => [],
    },
    placeholder: {
      type: String,
      default: "Click to select",
    },
    displayProperty: {
      type: String,
      default: "name",
    },
    valueProperty: {
      type: String,
      default: "value",
    },
  },
};
</script>

<style scoped>
.content {
  position: relative;
  background-color: #fff;
  top: 11px;
  right: 0;
  left: -10px;
  display: flex;
  padding: 5px 0;
  overflow-y: auto;
  min-width: 245px;
  min-height: 50px;
  box-shadow: 0 3px 3px 2px #e3e3e3;
}
.content_text {
  overflow: auto;
}
.container {
  position: relative;
  background-color: #fff;
  padding: 6px 12px;
  margin: 0 auto;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  height: 40px;
  max-width: 250px;
  display: flex;
  flex-wrap: wrap;
}
.content_checkbox {
  width: 22px;
  height: 22px;
  border: 1px solid #969696;
  margin-right: 7px;
  position: relative;
}
.content_checkbox--checked.content_checkbox {
  border: 1px solid #1f7bb8;
  background: #1f7bb8;
}
</style>
