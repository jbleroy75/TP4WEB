<template>
  <h1>HomePage</h1>
  <base-button>My BaseButton</base-button>
  <base-button disabled>My BaseButton disabled</base-button>
</template>

<script>
import BaseButton from "@/components/BaseButton";

export default {
  name: 'HomePage',
  components: {
    BaseButton,
  }
};
</script>

<style scoped></style>