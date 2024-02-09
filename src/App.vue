<script>
import ExampleName from "./components/ExampleName.vue";
import { store } from "./store";
import axios from "axios";

export default {
  components: {
    ExampleName,
  },
  data() {
    return {
      store,
    };
  },
  created() {
    this.requestRandomMail();
  },
  methods: {
    requestRandomMail() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/random/mail")
        .then((result) => {
          store.randomMail = result.data.response;
        });
    },
  },
};
</script>

<template>
  <h1>Hello World</h1>
  <h2>{{ store.helloValue }}</h2>
  <h3>axios request: {{ store.randomMail }}</h3>
  <ExampleName />
</template>

<style lang="scss">
@use "./styles/general.scss";

h2 {
  font-size: 120px;
  color: aquamarine;
}

h3 {
  font-size: 80px;
  color: blueviolet;
}
</style>
