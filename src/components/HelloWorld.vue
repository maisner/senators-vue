<template>
  <div class="flex">
    <div class="bg-white mx-auto rounded-xl p-8 shadow-lg">
      <div class="mb-2">
        <text-input name="login" placeholder="Login" ref="inputName" />
      </div>
      <div class="mb-2">
        <text-input name="password" placeholder="Heslo" isPassword ref="inputPassword" />
      </div>
      <div class="mt-8 text-center align-bottom h-auto">
        <button
          class="rounded-xl px-4 py-2 focus:outline-none bg-green-500 hover:bg-green-700 text-white"
          @click="onSubmit"
        >Odeslat</button>
      </div>
    </div>
  </div>
</template>

<script>
import TextInput from "./form/TextInput.vue";

export default {
  components: { TextInput },
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      name: "",
      password: "",
    };
  },
  methods: {
    validate(inputs) {
      let isValidate = true;

      inputs.forEach((input) => {
        if (!input.validate()) {
          isValidate = false;
          return;
        }
      });

      return isValidate;
    },
    onSubmit() {
      let inputs = [];

      let inputName = this.$refs.inputName;
      let inputPassword = this.$refs.inputPassword;

      inputs.push(inputName);
      inputs.push(inputPassword);

      if (!this.validate(inputs)) {
        return false;
      }

      let name = inputName.value;
      let pass = inputPassword.value;

      alert(`Přihlašovací údaje pro ${name} byly odeslány`);
    },
  },
};
</script>
