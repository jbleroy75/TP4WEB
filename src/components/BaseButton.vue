<template>
  <button>
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "BaseButton"
}
</script>

<style scoped>
button {
  color: white;
  background: #30cb92;
  border-radius: 5px;
  padding: 10px;
  border: none;
  font-weight: bold;
  margin: 5px;
}

button:hover {
  background: #28b682;
}

button:disabled {
  background: #6dcca5;
  cursor: not-allowed;
}
button:disabled:hover {
  background: #75dcb2;
}
</style>