<template>
  <div>
    <base-header/>
    <slot></slot>
    <base-footer/>
  </div>
</template>

<script>
import BaseHeader from '../components/BaseHeader.vue';
import BaseFooter from '../components/BaseFooter.vue';

export default {
  name: "BaseLayout",
  components: {
    BaseHeader,
    BaseFooter,
  },
}
</script>

<style scoped>

</style>