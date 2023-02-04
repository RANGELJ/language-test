<template>
  <div>Variable Statement</div>
</template>

<script setup lang="ts">
import {
  VariableStatement,
  SyntaxKind,
} from 'typescript';

// eslint-disable-next-line no-undef
const props = defineProps<{
  statement: VariableStatement;
}>();
</script>
