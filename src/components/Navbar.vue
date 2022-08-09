<template >
  <div class="shadow-4 bg-main">
    <!-- dark: bg-dark -->
    <div class="container d-flex justify-content-between py-3">
      <div>
        <router-link to="/" class="text-success text-decoration-none"
          >Home</router-link
        >
        |
        <router-link to="/about" class="text-secondary text-decoration-none"
          >About</router-link
        >
      </div>
      <div>
        <div
          @click="$emit('handle-darkmode-toggle')"  
        >
          <i class="fas fa-moon text-white" v-if="darkMode"></i>
          <i class="fas fa-sun" v-else></i>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navbar",
  props: {
    darkMode: Boolean,
  },
};
</script>

<style scoped>
button:hover {
  background-color: rgba(
    var(--bs-success-rgb),
    var(--bs-text-opacity)
  ) !important;
  color: #1c1c1e !important;
}
.fa-sun{
  color: #FDB813
}
.fas{
  cursor: pointer;
}

</style>
