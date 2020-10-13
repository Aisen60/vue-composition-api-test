<template>
  <h2>setup</h2>
  <p>props name:{{ name }}</p>
  <p>{{ count }}</p>
  <p>{{ object.foo }}</p>
  <slot />
</template>

<script>
import { h, ref, reactive, watchEffect } from "vue";
export default {
  props: {
    name: String,
  },

  /**
   * setup返回一个对象，这个对象的所有属性会被到当前组件模板
   * 它有两个参数，
   * 第一个是 props
   * 第二个是 content 上下文对象(attrs,emit,slots)
   * 注意 props 对象是响应式的，watchEffect 或 watch 会观察和响应 props 的更新：
   * 然而不要解构 props 对象，那样会使其失去响应性：
   */
  setup(props, context) {
    // console.log("context.attrs:", context.attrs);
    // console.log("context.emit:", context.emit);
    // console.log("context.slots:", context.slots);
    // watchEffect(() => {
    //   console.log(`更新后的props.name: ${props.name}`);
    // });

    return {
      count: ref(0),
      object: reactive({ foo: "bar" }),
    };
  },

  //   //   setup 也可以返回一个函数，函数中也能使用当前 setup 函数作用域中的响应式数据，经过实验发现，setup返回的vnode会覆盖当前 template 中的所有的节点。
  //   setup() {
  //     const count = ref(0);
  //     const object = reactive({ foo: "bar" });
  //     return () => h("div", [count.value, object.foo]);
  //   },
};
</script>
