<template>
  {{ count }}
  <br />
  {{ obj.count }}
</template>

<script>
import { ref, reactive, watch } from "vue";
export default {
  setup() {
    const count = ref(0),
      obj = reactive({ count: 10 });

    // //侦听单个数据源
    // watch(count, (newVal, oldVal) => {
    //   console.log("newVal:", newVal);
    //   console.log("oldVal:", oldVal);
    // });
    // setTimeout(() => {
    //   count.value++;
    // }, 1000);

    // //侦听多个数据源
    // const stopWatch = watch(
    //   [count, obj],
    //   ([newCount, newObj], [oldCount, oldObj]) => {
    //     console.log(`newCount: ${newCount}`);
    //     console.log(`newObj: ${newObj}`);
    //     console.log(`newObj.count: ${newObj.count}`);
    //     console.log(`oldCount: ${oldCount}`);
    //     console.log(`oldObj: ${oldObj}`);
    //     console.log(`oldObj.count: ${oldObj.count}`);
    //   },
    //   //深度监听，
    //   {
    //     deep: true,
    //   }
    // );

    // setTimeout(() => {
    //   count.value++;
    //   obj.count++;
    // }, 1000);

    // //会执行，但是不会进入到watch handler函数里面了
    // setTimeout(() => {
    //   count.value++;
    //   obj.count++;
    //   stopWatch(); // 取消监听
    // }, 2000);

    return {
      count,
      obj,
    };
  },
};
</script>
