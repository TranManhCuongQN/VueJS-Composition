<template>
  <div>
    <div class="card text-left mt-2">
      <div class="card-body text-center">
        <h4 class="card-title">Lifecycle</h4>
      </div>
    </div>
  </div>
</template>

<script>
import { onBeforeMount, onMounted } from "@vue/runtime-core";
export default {
  setup() {
    // setup() đại diện cho beforeCreate và created trong composition api.
    console.log("beforeCreate - created");
    onBeforeMount(() => {
      console.log("onBeforeMount");
    });
    onMounted(() => {
      console.log("onMounted");
    });
  },
};
</script>

<style></style>
