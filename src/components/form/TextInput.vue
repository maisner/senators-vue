<template>
  <span>
    <input
      :type="getType()"
      :name="name"
      class="input"
      :class="{'input-error': hasError()}"
      :placeholder="placeholder"
      v-model="value"
      @change="validate()"
      @keyup="validate()"
    />
  </span>
  <br />
  <div class="text-red-500 text-xs px-3 py-1">{{ this.error }}</div>
</template>

<script>
export default {
  name: "TextInput",
  props: {
    name: String,
    placeholder: String,
    default: String,
    isPassword: Boolean,
  },
  data() {
    return {
      value: "",
      error: "",
    };
  },
  mounted() {
    this.value = this.default;
  },
  methods: {
    getType() {
      return this.isPassword ? "password" : "text";
    },
    hasError() {
      return this.error.length > 0;
    },
    validate() {
      if (this.value.length === 0) {
        this.error = "Vyplňte prosím pole";

        return false;
      }

      if (this.value.length < 3) {
        this.error = "Zadená hodnota musí mít alespoň 3 znaky";

        return false;
      }

      this.error = "";
      return true;
    },
  },
};
</script>
