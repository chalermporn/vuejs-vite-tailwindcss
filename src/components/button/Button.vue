<script setup lang="ts">
import { computed } from 'vue';
const props = defineProps({
  color: {
    type: String,
    default: null,
  },
  label: {
    type: String,
    default: null,
  },
  icon: {
    type: String,
    default: null,
  },
  iconPos: {
    type: String,
    default: 'left',
  },
  iconClass: {
    type: String,
    default: null,
  },
  badge: {
    type: String,
    default: null,
  },
  badgeClass: {
    type: String,
    default: null,
  },
  loading: {
    type: Boolean,
    default: false,
  },
  loadingIcon: {
    type: String,
    default: 'pi pi-spinner pi-spin',
  },
});
const emit = defineEmits<{
  (e: 'click', status: boolean): boolean;
}>();
const click = () => {
  emit('click', true);
};

const buttonClass = computed(() => [
  { 'px-4 py-2': true },
  { 'gap-2 flex': props.icon },
  `border border-${props.color}-50 rounded-[4px] font-bold text-${props.color}-50 text-sm py-[${props.size}px]  group items-center hover:drop-shadow-lg`,
]);
</script>

<template>
  <button
    :class="buttonClass"
    type="button"
    :aria-label="defaultAriaLabel"
    :disabled="disabled"
  >
    <slot>
      <span v-if="loading && !icon" :class="iconStyleClass"></span>
      <span v-if="icon" :class="iconStyleClass"></span>
      <span class="p-button-label">{{ label || '&nbsp;' }}</span>
      <span v-if="badge" :class="badgeStyleClass">{{ badge }}</span>
    </slot>
  </button>
</template>
