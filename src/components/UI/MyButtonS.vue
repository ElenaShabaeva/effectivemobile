<template>
  <button class="button-s" :class="{ 'button-s--filled': filled }">
    <slot></slot>
  </button>
</template>

<script setup>
defineOptions({
  name: "my-button-s",
});
const props = defineProps({
  filled: {
    type: Boolean,
    default: false,
  },
});
</script>

<style lang="less">
.button-s {
  padding: 8px;
  border-radius: 4px;
  width: 36px;
  aspect-ratio: 1;
  border: 1px solid @gray-2;
  background-color: @light;
  color: @dark;

  &:hover {
    @media (hover: hover) {
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
        background-color: @purple-1;
      }
    }

    &:active {
      background-color: @purple-1;
    }
  }
}
</style>
