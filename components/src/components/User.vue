<template>
  <button type="button" @click="onClickAge">Update Age Event</button>
  <button type="button" @click="updateAgeFn(3)">Update Age CB</button>
  <p>The user is {{ age }} years old</p>
  <p>{{ ageDoubled }}</p>
</template>

<script>
export default {
  name: "User",
  data() {
    return {};
  },
  props: {
    age: {
      type: Number,
      required: true,
    },
    updateAgeFn: {
      type: Function,
      required: true,
    },
  },
  methods: {
    onClickAge() {
      this.$emit("age-change");
    },
  },
  computed: {
    ageDoubled() {
      return this.age * 2;
    },
  },
  emits: ["age-change"],
};
</script>

<style lang="scss" scoped></style>
