<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Hello Vue 3.0 + Vite" />
  <Setup :name="setupName"></Setup>

  <hr />
  <h2>reactive</h2>
  <Reactive />

  <hr />
  <h2>ref</h2>
  <RefComponent />

  <hr />
  <h2>computed</h2>
  <ComputedComponent />

  <hr />
  <h2>watch</h2>
  <WatchComponent />

  <hr />
  <h2>watchEffect</h2>
  <WatchEffectComponent />

  <hr />
  <h2>生命周期</h2>
  <LifecycleHooks />
</template>

<script>
import { ref } from "vue";

import HelloWorld from "./components/HelloWorld.vue";
import Setup from "./components/Setup.vue";
import Reactive from "./components/Reactive.vue";
import RefComponent from "./components/Ref.vue";
import ComputedComponent from "./components/Computed.vue";
import WatchComponent from "./components/Watch.vue";
import WatchEffectComponent from "./components/WatchEffect.vue";
import LifecycleHooks from "./components/LifecycleHooks.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    Setup,
    Reactive,
    RefComponent,
    ComputedComponent,
    WatchComponent,
    WatchEffectComponent,
    LifecycleHooks,
  },
  setup() {
    const setupName = ref("aaaaa");
    return {
      setupName,
    };
  },
  methods: {
    updateData() {
      console.log(this.setupName);
    },
  },
  created() {
    setTimeout(() => {
      this.setupName = "bbbbb";
    }, 2000);
  },
};
</script>
