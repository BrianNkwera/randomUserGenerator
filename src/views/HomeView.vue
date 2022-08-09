<template>
  <div class="home pt-5 text-center bg-main h-100">
    <div class="mx-auto">
      <Spinner v-if="!contentLoaded" />
      <div v-else class="height-custom">
        <Image :imgUrl="image" :imgAlt="`${firstName} ${lastName}`" />
        <Name :username="`${firstName} ${lastName}`" />
      </div>
      <Button @handle-button-click="getUser" />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Button from "@/components/Button.vue";
import Image from "@/components/Image.vue";
import Name from "@/components/Name.vue";
import Spinner from "@/components/Spinner.vue";

export default {
  name: "HomeView",
  components: {
    Name,
    Image,
    Button,
    Spinner,
  },
  /*data() is like constructor of a class they are used
   *to initialize components
   */
  data() {
    return {
      firstName: "Brian",
      lastName: "Nkwera",
      image:
        "https://fitabo-bucket.s3.us-east-1.amazonaws.com/Mainpicture-min.JPG",
      contentLoaded: false,
    };
  },

  /** methods are like setters, used to add data on components */
  methods: {
    async getUser() {
      this.contentLoaded = false;
      const respose = await fetch("https://randomuser.me/api");
      const { results } = await respose.json();

      this.firstName = results[0].name.first;
      this.lastName = results[0].name.last;
      this.image = results[0].picture.large;
      this.contentLoaded = true;
    },
  },

  created() {
    this.contentLoaded = true;
  },
};
</script>
