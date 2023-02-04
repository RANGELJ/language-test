<template>
  <div>Unknown Statement kind: {{ statementKind }}</div>
</template>

<script setup lang="ts">
import {
  computed,
} from 'vue';
import {
  Statement,
  SyntaxKind,
} from 'typescript';

// eslint-disable-next-line no-undef
const props = defineProps<{
  statement: Statement;
}>();

const statementKind = computed(() => SyntaxKind[props.statement.kind]);
</script>
