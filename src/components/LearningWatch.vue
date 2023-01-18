<template>
  <div>
    <div class="card text-left mt-2">
      <div class="card-body text-center">
        <h4 class="card-title">Watch</h4>
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
import { ref, watch } from "vue";
export default {
  setup() {
    const count = ref(1);

    const handleIncrementCount = () => {
      count.value++;
    };

    // thứ nhất biến  mình cần theo dõi
    // thứ hai là function để giải quyết vấn đề mỗi lần biến này thay đổi
    watch(count, function (newValue, olaValue) {
      console.log("newValue", newValue);
      console.log("olaValue", olaValue);
      if (newValue > 10) {
        count.value = 1;
      }
    });

    return {
      count,
      handleIncrementCount,
    };
  },
};
</script>

<style></style>
