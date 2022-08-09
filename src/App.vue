<template>
  <div :class="[darkMode&&'dark', 'vh-100']">
    <Navbar :darkMode="darkMode" @handle-darkmode-toggle="toggleDarkMode" />
    <router-view />
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
export default {
  name: "App",
  components: {
    Navbar,
  },
  data() {
    return {
      darkMode: false,
    };
  },
  methods: {
    toggleDarkMode() {
      this.darkMode = !this.darkMode;
    },
  },
};
</script>


<style lang="scss">


</style>
