<template>
  <div>
    <div class="card text-left">
      <div class="card-body text-center">
        <h4 class="card-title">Reactivity</h4>
        <p class="card-text">{{ user.name }}</p>
        <p class="card-text">{{ user.age }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import { isReactive, isRef, reactive, ref } from "vue";
export default {
  setup() {
    // Khai báo bằng ref thì nó đồng bộ với nhau về mặt bộ nhớ. Nếu nó thay đổi thì nó sẽ thay đổi luôn. Nếu cách ta khai báo chuỗi bình thường (thiên về mặt value) thì nó sẽ không đồng bộ với nhau. Cái nào thay đổi thì chỉ có cái đó thay đổi thôi.
    // sử dụng ref cho những loại dữ liệu nguyên thử như string, number, boolean, null, undefined
    let userName = ref("Hello World");
    let userAge = ref(22);

    // đối với dạng tham chiếu object/array thì sử dụng reactive
    let user = reactive({
      name: "Hello World",
      age: 22,
    });

    setTimeout(() => {
      userName.value = "Hello Vue 3";
      userAge.value = 22;
      user.name = "Hello Vue 3";
      user.age = 25;
    }, 2000);

    console.log(isRef(userName));
    console.log(isReactive(user));

    return {
      userName,
      userAge,
      user,
    };
  },
};
</script>

<style></style>
