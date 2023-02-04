<template>
  <div class="tsSourceFileRendererFrame">
    <div>Source file name: {{ sourceFile.fileName }}</div>
    <div>
      <TsStatementRenderer
        v-for="(statement, statementIndex) in sourceFile.statements"
        :key="statementIndex"
        :statement="statement"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import TsStatementRenderer from '@/components/TsStatementRenderer.vue';
import { watchEffect } from 'vue';
import type {
  SourceFile,
} from 'typescript';

// eslint-disable-next-line no-undef
const props = defineProps<{
  sourceFile: SourceFile;
}>();

watchEffect(() => {
  console.log(props.sourceFile);
});
</script>

<style scoped>
.tsSourceFileRendererFrame {
  width: 100%;
  height: 100%;
  border-width: 1px;
  border-style: solid;
  display: flex;
  flex-direction: column;
}
</style>
