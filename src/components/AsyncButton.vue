<template>
  <base-button
      :disabled="isPending"
      :color="color"
      @click.stop.prevent="handleClick"
  >
    <span v-if="isPending">Loading.. </span>
    <slot/>
  </base-button>
</template>

<script>
import BaseButton from './BaseButton.vue'

export default {
  name: 'AsyncButton',
  components: {BaseButton},
  inheritAttrs: false,

  props: {
    color: {
      type: String,
      default: 'primary'
    }
  },

  data() {
    return {
      isPending: false
    }
  },

  methods: {
    handleClick() {
      if (this.isPending)
        return;
      this.isPending = true
      setTimeout(() => this.isPending = false, 2000);
    }
  }
}
</script>
<style scoped>

</style>