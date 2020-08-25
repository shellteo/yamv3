<template>
  <button
    :type="type || 'button'"
    @click="$emit('click')"
    class="button"
    :disabled="loading"
  >
    <UiLoading v-if="loading" />
    <slot v-else />
  </button>
</template>

<script>
export default {
  props: {
    loading: Boolean,
    type: String
  }
};
</script>

<style scoped lang="scss">
@import '../../vars';

.button {
  border: 1px solid $border-color;
  background-color: transparent;
  color: #5b2739;
  border-radius: 23px;
  padding: 0 24px;
  outline: none;
  line-height: 46px;
  height: 46px;
  font-size: 18px;

  &.button--submit {
    background-color: $bg-blue;
    border: 1px solid $bg-blue;

    &:hover {
      color: #5b2739;
      background-color: $bg-blue;
      border: 1px solid $bg-blue;
    }

    &:disabled {
      color: #5b2739 !important;
      border: 1px solid $text-gray;
      background-color: $text-gray;
    }
  }

  &:hover {
    color: #5b2739;
    border-color: #5b2739;
  }

  &:disabled {
    color: $text-gray !important;
    cursor: not-allowed;
  }
}
</style>
