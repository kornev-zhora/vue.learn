<template>
  <h2>Component</h2>
  <p>This is the component</p>
  <p id="pResult">{{ text }}</p>
</template>

<script>
export default {
  data() {
    return {
      text: '...'
    }
  },
  beforeCreate() {
    this.text = 'initial text';
    console.log("beforeCreate: The component is not created yet.");
  }
}
</script>