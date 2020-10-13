<script>
import { ref, reactive, watchEffect } from "vue";
export default {
  setup() {
    const count = ref(0),
      obj = reactive({ count: 10 });
    let test = 100;
    watchEffect((a) =>
      console.log("watchEffect 追踪依赖:", count.value, obj.count, test)
    );
    setTimeout(() => {
      count.value++;
      obj.count++;
      test++;
    }, 1000);
  },
};
</script>
