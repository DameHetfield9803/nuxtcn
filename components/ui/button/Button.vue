<template>
  <button :class="buttonClass">
    <slot />
  </button>
</template>

<script setup lang="ts">
import { computed } from 'vue'
import { buttonVariants } from '.'
import type { ButtonVariants } from '.'

interface Props {
  variant?: ButtonVariants['variant']
  size?: ButtonVariants['size']
  class?: string
}

const props = withDefaults(defineProps<Props>(), {
  variant: 'default',
  size: 'default'
})

const buttonClass = computed(() => {
  return buttonVariants({ variant: props.variant, size: props.size, class: props.class })
})

defineOptions({
  name: 'Button',
  inheritAttrs: false,
})
</script>
