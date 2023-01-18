<template>
  <div>
    <div class="card text-left mt-2">
      <div class="card-body text-center">
        <h4 class="card-title">Computed</h4>
        <div class="form-group">
          <label for="firstName">First Name</label>
          <!-- <input
            type="text"
            class="form-control"
            id="firstName"
            placeholder="First name"
            @input="setFirstName"
          /> -->

          <input
            type="text"
            class="form-control"
            id="firstName"
            placeholder="First name"
            v-model="firstName"
          />
        </div>
        <div class="form-group">
          <label for="lastName">Last Name</label>
          <!-- <input
            type="text"
            class="form-control"
            id="lastName"
            placeholder="Last name"
            @input="setLastName"
          /> -->

          <input
            type="text"
            class="form-control"
            id="lastName"
            placeholder="Last name"
            v-model="lastName"
          />
        </div>
        <h3>
          <!-- <span class="badge badge-info"
            >Họ và tên: {{ firstName }} {{ lastName }}</span
          > -->
          <span class="badge badge-info">Họ và tên : {{ fullName }}</span>
        </h3>
      </div>
    </div>
  </div>
</template>

<script>
import { ref, computed } from "vue";
export default {
  setup() {
    const firstName = ref("");
    const lastName = ref("");

    function setLastName(event) {
      lastName.value = event.target.value;
    }
    function setFirstName(event) {
      firstName.value = event.target.value;
    }

    const fullName = computed(() => {
      return `${firstName.value} ${lastName.value}`;
    });

    return {
      // trả về object
      setLastName,
      setFirstName,
      lastName,
      firstName,
      fullName, // fullName: fullName
    };
  },
};
</script>

<style></style>
