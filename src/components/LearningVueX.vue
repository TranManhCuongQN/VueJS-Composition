<template>
  <div>
    <div class="card text-left mt-2">
      <div class="card-body text-center">
        <h4 class="card-title">VueX</h4>
        <h3>
          <span class="badge badge-success">count : {{ count }}</span>
        </h3>
        <button class="btn btn-danger" @click="handleIncrementCount">
          increment count
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import { computed } from "@vue/runtime-core";
import { useStore } from "vuex";
export default {
  setup() {
    // this.$store ==>store
    const store = useStore();
    const count = computed(() => store.state.count);

    // dispatch action, commit mutation
    const handleIncrementCount = () => {
      store.dispatch("incrementAction");
    };
    return {
      count,
      handleIncrementCount,
    };
  },
};
</script>

<style></style>
