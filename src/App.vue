<script>
import LearningReactivity from "./components/LearningReactivity.vue";
import LearningProps from "./components/LearningProps.vue";
import LearningMethod from "./components/LearningMethod.vue";
import LearningComputed from "./components/LearningComputed.vue";
import LearningWatch from "./components/LearningWatch.vue";
import LearningRefTemplate from "./components/LearningRefTemplate.vue";
import LearningProvideInject from "./components/LearningProvideInject.vue";
import LearningLifecycle from "./components/LearningLifecycle.vue";
import LearningVueX from "./components/LearningVueX.vue";
import { provide, ref } from "vue";
export default {
  name: "App",
  components: {
    LearningReactivity,
    LearningProps,
    LearningMethod,
    LearningComputed,
    LearningWatch,
    LearningRefTemplate,
    LearningProvideInject,
    LearningLifecycle,
    LearningVueX,
  },
  setup() {
    const age = ref(22);
    provide("name", "Nguyen Van A");
    provide("age", age);
  },
};
</script>

<template>
  <main class="container">
    <learning-reactivity />
    <learning-props
      image="https://i.pinimg.com/564x/24/d9/05/24d9054645081ff1b1543f4586aa4e81.jpg"
    />
    <learning-method />
    <learning-computed />
    <learning-watch />
    <learning-ref-template />
    <learning-provide-inject />
    <learning-lifecycle />
    <learning-vue-x />
  </main>
</template>

<style scoped></style>
