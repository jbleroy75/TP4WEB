<template>
  <base-button
      :color="color"
      @click.stop.prevent="handleClick"
  >
    <span v-if="isPending">Loading.. {{currentTime}}: </span>
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
      isPending: false,
      currentTime: 0
    }
  },

  methods: {
    handleClick() {
      if (this.isPending === true) {
        this.currentTime++;
        return;
      }

      this.isPending = true
      this.currentTime = 2
      var timer = setInterval(() => {
        if (--this.currentTime === 0) {
          this.isPending = false
          clearInterval(timer);
        }
      }, 1000);
    }
  }
}
</script>
<style scoped>

</style>