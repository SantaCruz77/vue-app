<script setup>
import { reactive } from "vue";
import axios from "axios";
import Title from "./components/Title.vue";
import Form from "./components/Form.vue";
import Results from "./components/Results.vue";

const results = reactive({
  country: "",
  cityName: "",
  temperature: "",
  conditionText: "",
  icon: "",
});

const getWeather = () => {
  axios
    .get(
      "https://api.weatherapi.com/v1/current.json?key=1ebb115188054f369fa11205232103&q=London&aqi=no"
    )
    .then((res) => console.log(res));
};
</script>

<template>
  <Title />
  <Form @submit-form="getWeather" />
  <Results />
</template>
