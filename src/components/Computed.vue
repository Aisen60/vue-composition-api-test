<template>
  <p>{{ comput1 }}</p>
</template>

<script>
import { ref, computed } from "vue";
export default {
  setup() {
    const computCount = ref(100);
    const comput1 = computed(() => computCount.value * 3);
    const comput2 = computed({
      get: () => computCount.value * 2,
      set: (val) => {
        computCount.value = val;
      },
    });
    comput2.value = 300;
    // console.log(comput2.value); // 结果：600
    return {
      comput1,
    };
  },
};
</script>
