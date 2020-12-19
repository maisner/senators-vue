<template>
  <main class="min-h-screen bg-gradient-to-r from-gray-50  to-gray-200">
    <section class="">
      <h1 class="text-center text-5xl text-gray-400 py-24">HC Senators</h1>
      <HelloWorld msg="Hello Vue 3.0 + Vite" />
    </section>
  </main>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
  },
};
</script>
