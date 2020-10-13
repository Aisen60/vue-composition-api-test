<template>
  {{ count }}
</template>

<script>
import {
  ref,
  onBeforeMount,
  onMounted,
  onBeforeUpdate,
  onUpdated,
  onBeforeUnmount,
  onUnmounted,
  onRenderTracked,
  onRenderTriggered,
} from "vue";
export default {
  setup() {
    console.log("初始化");
    const count = ref(0);

    onBeforeMount(() => {
      console.log("挂载前");
    });
    onMounted(() => {
      console.log("挂载时");
    });
    onBeforeUpdate(() => {
      console.log("更新前");
    });
    onUpdated(() => {
      console.log("更新时");
    });
    onBeforeUnmount(() => {
      console.log("摧毁前");
    });
    onUnmounted(() => {
      console.log("摧毁后");
    });
    onRenderTracked((e) => {
      console.log(e);
    });
    onRenderTriggered((e) => {
      console.log(e);
    });

    setTimeout(() => {
      count.value++;
    }, 1000);

    return { count };
  },
};
</script>
