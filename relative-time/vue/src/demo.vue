<template>
  <div class="demo" :lang="lang">
    <select v-model="lang">
      <option v-for="lang in langs">
        {{lang}}
      </option>
    </select>

    <date-input v-model="date" />
    <relative-time :lang="lang" :dateTime="date" />
  </div>
</template>

<script>
  import {sample} from "lodash-es"
  import DateInput from "./date-input"
  import moment from "moment"

  console.log(moment.locales())

  export default {
    components: {
      "date-input": DateInput,
    },

    data: () => ({
      date: new Date,
      lang: sample(moment.locales()),
      langs: moment.locales(),
    }),
  }
</script>

<style>
  .demo {
    border: 1px solid black;
  }
</style>
