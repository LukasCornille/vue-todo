<template>
  <div class="todo-list">
    <Item
      v-for="(todoItem, index) in todoList"
      :key="index"
      :todoItem="todoItem"
      @toggle-completed="$emit('toggle-completed', index)"
      @remove-from-list="$emit('remove-from-list', index)"
    />
  </div>
</template>

<script setup lang="ts">
import { defineProps, defineEmit } from 'vue';
import Item from './Item.vue';

defineProps<{ todoList: TodoItem[] }>();
defineEmit({
  'toggle-completed': (index: number) => true,
  'remove-from-list': (index: number) => true,
});
</script>
