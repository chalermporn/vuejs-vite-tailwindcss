<script setup lang="ts">
import { reactive } from 'vue';
import Button from './components/button/Button.vue';

const data = reactive({
  content: [
    {
      name: 'demo1',
      value: 0,
    },
    {
      name: 'demo2',
      value: 0,
    },
  ],
});
</script>

<template>
  <div class="flex flex-col gap-2">
    <h5>Basic</h5>
    <div class="flex flex-row gap-2">
      <Button label="Submit" color="primary" />
      <Button label="Disabled" :disabled="true" />
      <Button label="Link" class="p-button-link" />
    </div>
    <table>
      <tr>
        <td>name</td>
        <td>value</td>
      </tr>
      <tr v-for="(item, index) in data.content" :key="index">
        <td>
          {{ item.name }}
        </td>
        <td>
          {{ item.value }}
          <input type="text" v-model="item.value" />
        </td>
      </tr>
    </table>
  </div>
</template>
