<template>
  <div class="input">
    <label
      :for="inputName"
      class="input__label"
      :class="{ 'is-hidden': hidden }"
      >{{ label }}</label
    >
    <input
      class="input__field"
      :class="{ 'input__field--error': error }"
      :id="inputName"
      :type="type"
      :placeholder="placeholder"
      :value="modelValue"
      :required="required"
      :aria-describedby="`desc-${inputName}`"
      @input="updateInput"
    />
    <span
      class="input__error"
      :id="`desc-${inputName}`"
      role="alert"
      v-if="error"
      >{{ error }}</span
    >
  </div>
</template>

<script setup>
defineOptions({
  name: "my-input",
});

const props = defineProps({
  modelValue: [String, Number],
  label: {
    type: String,
    required: true,
  },
  inputName: String,
  required: Boolean,
  error: String,
  hidden: {
    type: Boolean,
    default: true,
  },
  type: {
    type: String,
    default: "text",
  },
  placeholder: String,
});
const emit = defineEmits(["update:modelValue", "blur"]);
const updateInput = (event) => {
  emit("update:modelValue", event.target.value);
};
</script>

<style lang="less">
.input {
  position: relative;
  display: flex;
  flex-direction: column;
  row-gap: 4px;

  &__field {
    padding: 8px 48px 8px 12px;
    border: 1px solid @gray-2;
    background-color: @light;
    border-radius: 8px;
    height: 44px;
    transition: all 0.3s;

    &:hover {
      @media (hover: hover) {
        border: 1px solid @blue;
      }
    }

    &--error {
      border-color: @red;
    }
  }

  &__label,
  &__error {
    font-size: 14px;
    line-height: 1.42;
  }

  &__error {
    position: absolute;
    bottom: -16px;
    left: 0;
    color: @red;
  }
}
</style>
