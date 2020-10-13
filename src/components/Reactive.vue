<template>
  <p>{{ object.foo }}</p>
</template>

<script>
import { reactive } from "vue";
export default {
  setup() {
    const object = reactive({ foo: "bar" });
    return {
      object,
    };
  },
};
</script>
