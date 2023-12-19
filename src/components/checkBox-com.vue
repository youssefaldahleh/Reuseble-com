<template>
  <div class="container">

    <input type="checkbox" :required="required" :value="value" v-model="model" />
    <label class="label-inline">{{ label }}</label>
  </div>
</template>
<script>
export default {
  props: {
    label: {
      type: String,
      default: "",
    },
    required: {
      type: Boolean,
      default: false,
    },
    hintMessage: {
      type: String,
      default: "",
    },
    errorMessage: {
      type: String,
      default: "",
    },
    modelValue: {
      type: [Array, Boolean],
    },
    value: {
      type: [String, Array],
    },
  },

  data() {
    return {
      innerValue: null,
    };
  },

  computed: {
    model: {
      get() {
        return this.modelValue;
      },
      set(value) {
        this.$emit("update:modelValue", value);
      },
    },
  },
};
</script>
