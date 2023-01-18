<template>
  <div>
    <div class="card text-left mt-2">
      <div class="card-body text-center">
        <h4 class="card-title">Provide/Inject</h4>
        <p>{{ name }} -- {{ age }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import { inject } from "vue";
export default {
  setup() {
    // Nếu bên app ko truyền tham số name thì nó lấy mặc định là Hello world
    const name = inject("name", "Hello world");
    const age = inject("age");

    setInterval(() => {
      age.value++;
    }, 2000);

    return {
      name,
      age,
    };
  },
};
</script>

<style></style>
