<template>
  <p v-if="age > 25">{{ message }}</p>
  <p v-else>You must be 25 years or older to view this message</p>
</template>

<script>
export default {
  name: "Greeting",
  data() {
    return {};
  },
  props: {
    message: {
      type: String,
      required: true,
    },
    age: {
      type: Number,
      required: true,
    },
  },
};
</script>

<style scoped lang="scss">
h1 {
  color: red;
  text-align: center;
  &:hover {
    color: darken(#cc4444, 15%);
  }
}
</style>
