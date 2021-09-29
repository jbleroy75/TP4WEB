<template>
  <button :style="getStyle">
    <slot></slot>
  </button>
</template>

<script>
const colorPalette = {
  primary: {bg: '#42b983', hoverBg: '#4cce93', disabledBg: '#9ed3bf', focusBorder: '#47d696'},
  warn: {bg: '#ff5722', hoverBg: '#ff7043', disabledBg: '#ccaca2', focusBorder: '#ff8a65'},
  danger: {bg: '#e53935', hoverBg: '#ef5350', disabledBg: '#cca3a3', focusBorder: '#e57373'},
}

export default {
  name: "BaseButton",
  props: {
    color: {
      type: String,
      default: 'primary'
    }
  },
  computed: {
    getStyle: function () {
      let color = colorPalette[this.color];
      return {
        '--background': color.bg,
        '--background-hover': color.hoverBg,
        '--border-hover': "solid 1px " + color.focusBorder,
        '--background-hover-disabled': color.hoverBg
      }
    }
  }
}
</script>

<style scoped>
button {
  color: white;
  border-radius: 5px;
  padding: 10px;
  border: solid 1px #ececec;
  font-weight: bold;
  margin: 5px;
  background: var(--background);
}

button:hover {
  background: var(--background-hover);
  border: var(--border-hover);
}

button:disabled {
  background: var(--background-hover-disabled);
  cursor: not-allowed;
}
</style>