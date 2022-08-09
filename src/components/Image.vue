<template>
  <img
    class="my-4 border border-success rounded-circle border-5"
    :src="imgUrl"
    :alt="imgAlt"
    srcset=""
  />
</template>

<script>
export default {
  name: "Image",
  props: {
    imgUrl: String,
    imgAlt: String,
  },
};
</script>

<style scoped>
img {
  height: 120px;
  width: 120px;
}
</style>