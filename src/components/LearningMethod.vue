<template>
  <div>
    <div class="card text-left">
      <div class="card-body text-center">
        <h4 class="card-title">Method</h4>
        <p class="card-text">{{ user.name }}</p>
        <p class="card-text">{{ user.age }}</p>
        <button class="btn btn-success" @click="handleClick">Change</button>
      </div>
    </div>
  </div>
</template>

<script>
import { reactive, ref } from "vue";
export default {
  setup() {
    let userName = ref("Hello World");
    let userAge = ref(22);

    let user = reactive({
      name: "Hello World",
      age: 22,
    });

    function handleClick() {
      userName.value = "Hello Vue 3";
      userAge.value = 28;
      user.name = "Hello Vue 3";
      user.age = 28;
    }

    return {
      userName,
      userAge,
      user,
      handleClick,
    };
  },
};
</script>

<style></style>
