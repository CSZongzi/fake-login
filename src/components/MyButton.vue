<script lang="ts" setup>
defineProps({
  loading: Boolean,
});
</script>

<template>
  <button class="my-button">
    <span>
      <slot></slot>
    </span>
    <div v-if="loading" class="icon">
      <img src="@/assets/rolling.gif" alt="" />
    </div>
    <div v-else class="icon">
      <slot name="icon"></slot>
    </div>
  </button>
</template>

<style lang="scss">
.my-button {
  padding: 0.75rem 1.25rem;
  margin-top: 1rem;
  color: #fff;
  background-color: #2080f0;
  border: none;

  &:hover,
  &:focus {
    background-color: #1c73d8;
  }

  span {
    display: block;
    float: left;
    padding-right: 1rem;
    font-size: 1rem;
  }

  .icon {
    float: right;

    img {
      display: block;
      width: 1.375rem;
      height: 1.375rem;
    }

    svg {
      display: block;
      width: 1.375rem;
      height: 1.375rem;
    }
  }
}
</style>
