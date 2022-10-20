<template>
  <AppForm>
    <template v-slot:helps>
      <p>{{ help }}</p>
    </template>
    <template v-slot:fields>
      <input type="email" placeholder="email" />
      <input type="text" placeholder="username" />
      <input type="password" placeholder="password" />
    </template>
    <template v-slot:buttons>
      <button type="button">Submit</button>
    </template>
    <p>Dummy text</p>
  </AppForm>
  <AppForm>
    <template v-slot:helps>
      <p>Contact help text</p>
    </template>
    <template v-slot:fields>
      <input type="text" placeholder="name" />
      <input type="text" placeholder="message" />
    </template>
    <template v-slot:buttons>
      <button type="button">sent</button>
    </template>
  </AppForm>
</template>

<script>
import AppForm from "./components/Form.vue";

export default {
  name: "App",
  components: {
    AppForm,
  },
  data() {
    return {
      help: "This is some help text",
    };
  },
};
</script>
<style lang="scss"></style>
