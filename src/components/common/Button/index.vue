<template>
  <button
    class="btn"
    :class="{ [`btn--${props.variant ?? 'outlined'}`]: true }"
  >
    <slot />
  </button>
</template>

<script setup lang="ts">
// Default variant is `outlined`
type T_ButtonVariants = "primary" | "outlined" | "ghot";

interface I_ButtonProps {
  variant?: T_ButtonVariants;
}

const props = defineProps<I_ButtonProps>();
</script>

<style scoped lang="scss">
@import "~/assets/style/mixins.scss";

.btn {
  outline: none;
  border: none;
  padding: 8px 14px;
  border: 2px solid var(--c-primary);
  background: transparent;
  cursor: pointer;
  transition: transform var(--transition);

  &--primary {
    color: #fff;
    background: var(--c-primary);
  }

  &--ghot {
    border-color: transparent;
    background: transparent;
  }

  &:active {
    transform: scale(0.9);
  }
}
</style>
