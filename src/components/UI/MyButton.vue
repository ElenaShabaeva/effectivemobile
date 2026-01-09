<template>
  <button class="button" :class="{ 'button--filled': filled }">
    <slot></slot>
  </button>
</template>

<script setup>
defineOptions({
  name: "my-button",
});
const props = defineProps({
  filled: {
    type: Boolean,
    default: false,
  },
});
</script>

<style lang="less">
.button {
  padding: 16px 32px;
  border-radius: 16px;
  border: 1px solid @gray-2;
  background-color: @light;

  &:hover {
    @media (hover: hover) {
      border-radius: 8px;
      background-color: @gray-1;
    }
  }

  &:active {
    background-color: @gray-1;
  }

  &--filled {
    border: 1px solid @purple;
    background-color: @purple;
    color: @light;

    &:hover {
      @media (hover: hover) {
        border-radius: 8px;
        background-color: @purple-1;
      }
    }

    &:active {
      background-color: @purple-1;
    }
  }
}
</style>
