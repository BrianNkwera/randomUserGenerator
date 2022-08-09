<template>
  <button
    @click="$emit('handle-button-click')"
    class="mx-auto btn btn-success mt-4 border border-success text"
  >
  <!-- dark: btn-dark tex-dark -->
    Generate random user
  </button>
</template>

<script>
export default {
  name: "Button",
  /* These are properties of a component */
  props: {
    /** Can also use [prop1,prop2] 
     * Also you can use 
     * propName: {
     * type: type,
     * default: defaultValueOfProp
     * }
    */
    imgUrl: String,
    imgAlt: String,
  },
  emits: ["handle-button-click"]

};
</script>

<style scoped>

</style>
