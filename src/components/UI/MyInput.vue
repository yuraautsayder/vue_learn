<template>
  <input
    :value="modelValue"
    @input="updateInput"
    class="post-input"
    type="text"
  />
</template>
<script>
export default {
  name: "my-input",
  props: {
    modelValue: [String, Number],
  },
  methods: {
    updateInput(event) {
      this.$emit("update:modelValue", event.target.value);
    },
  },
};
</script>
<style scoped>
.post-input {
  width: 100%;
  border: 1 solid #efefef;
  padding: 10px 15px;
  margin-top: 30px;
}
</style>
