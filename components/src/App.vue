<template>
  <h1>Hi There!</h1>
  <Greeting :message="message" :age="age" />
  <!--v-on or @ -->
  <User :age="age" @age-change="age++" :updateAgeFn="updateAgeCB" />
</template>

<script>
import Greeting from "./components/Greeting.vue";
import User from "./components/User.vue";

export default {
  name: "App",
  components: {
    Greeting,
    User,
  },
  data() {
    return {
      message: "Hello world",
      age: 20,
    };
  },
  methods: {
    updateAgeCB(num) {
      this.age += num;
    },
  },
};
</script>

<style lang="scss">
body {
  text-align: center;
}
</style>
