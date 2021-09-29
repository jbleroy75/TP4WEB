<template>
  <h1>HomePage</h1>
  <base-button color="primary">My BaseButton</base-button>
  <base-button color="warn" disabled>My BaseButton</base-button>
  <base-button color="warn">My BaseButton</base-button>
  <base-button color="danger" disabled>My BaseButton</base-button>
  <base-button color="danger">My BaseButton</base-button>
  <base-button disabled>My BaseButton disabled</base-button>
  <async-button>My AsyncButton</async-button>
</template>

<script>
import BaseButton from "@/components/BaseButton";
import AsyncButton from "@/components/AsyncButton";

export default {
  name: 'HomePage',
  components: {
    BaseButton,
    AsyncButton
  }
};
</script>

<style scoped></style>