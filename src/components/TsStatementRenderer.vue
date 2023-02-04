<template>
  <component
    :is="statementComponent"
    :statement="statement"
  />
</template>

<script setup lang="ts">
import TsStatementUnknownRenderer from '@/components/TsStatementUnknownRenderer.vue';
import TsVariableStatementRenderer from '@/components/TsVariableStatementRenderer.vue';
import {
  computed,
} from 'vue';
import {
  Statement,
  SyntaxKind,
  isVariableStatement,
} from 'typescript';

// eslint-disable-next-line no-undef
const props = defineProps<{
  statement: Statement;
}>();

const statementComponent = computed(() => {
  if (isVariableStatement(props.statement)) {
    return TsVariableStatementRenderer;
  }
  return TsStatementUnknownRenderer;
});
</script>
