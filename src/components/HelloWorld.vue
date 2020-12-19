<template>
  <div class="flex">
    <div class="bg-white mx-auto rounded-xl h-60 p-8 shadow-lg">
      <div class="mb-2">
        <input
          type="text"
          class="rounded-xl bg-gray-100 focus:bg-gray-200 h-8 p-6"
          placeholder="Jméno"
        />
      </div>
      <div class="mb-2">
        <input
          type="text"
          class="rounded-xl bg-gray-100 focus:bg-gray-200 h-8 p-6"
          placeholder="Heslo"
        />
      </div>
      <div class="mt-8 text-center align-bottom h-auto">
        <input type="submit" class="rounded-xl px-4 py-2 bg-green-400" value="Odeslat">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      count: 0,
    };
  },
};
</script>
