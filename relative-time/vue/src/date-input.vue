<template>
  <input type=date :value-as-date.prop="value" @input="handleInput">
</template>

<script>
  export default {
    props: [
      "value",
    ],

    methods: {
      handleInput(evt) {
        this.$emit("input", evt.target.valueAsDate)
      },
    },
  }
</script>
