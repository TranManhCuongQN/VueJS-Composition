<template>
  <div class="card text-left mt-2">
    <div class="card-body text-center">
      <h4 class="card-title">Props</h4>
      <img :src="image" alt="" class="img-thumbnail" />
    </div>
  </div>
</template>

<script>
import { toRefs } from "vue";
export default {
  props: {
    image: String,
  },
  setup(props) {
    const { image } = toRefs(props);
    console.log(image.value);
  },
};
</script>

<style></style>
