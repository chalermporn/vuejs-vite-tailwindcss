<script setup lang="ts">
import Button from './components/button/Button.vue';
</script>

<template>
  <div class="flex flex-col gap-2">
    <h5>Basic</h5>
    <div class="flex flex-row gap-2">
      <Button label="Submit" color="primary" />
      <Button label="Disabled" :disabled="true" />
      <Button label="Link" class="p-button-link" />
    </div>
  </div>
</template>
