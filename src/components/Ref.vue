<template>
  <span>
    {{ count }}
  </span>
</template>
<script>
import { reactive, ref } from "vue";
const staticCount = ref(0);
export default {
  setup() {
    /**
     * ref
     * 接收一个普通的值返回一个响应式且可改变的ref对象，ref 对象拥有一个指向内部值的单一属性 .value。
     * 模板中访问:当 ref 作为渲染上下文的属性返回（即在setup() 返回的对象中）并在模板中使用时，它会自动解套，无需在模板内额外书写 .value
     * 作为响应式对象的属性访问:当 ref 作为 reactive 对象的 property 被访问或修改时，也将自动解套 value 值，其行为类似普通属性：
     * 注意当嵌套在 reactive Object 中时，ref 才会解套。从 Array 或者 Map 等原生集合类中访问 ref 时，不会自动解套
     */
    const count = ref(0);
    const array = reactive([ref(0)]);
    // console.log(count.value); // 结果：0
    // console.log(array[0].value); // 结果：0
    return {
      count,
      array,
    };
  },
};
</script>
