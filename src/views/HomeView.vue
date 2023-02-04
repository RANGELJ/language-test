<template>
  <div class="editorContainer">
    <textarea
      class="codeEditor"
      aria-label="Code editor"
      v-model="sourceCode"
    />
    <div class="renderContainer">
      <TsSourceFileRenderer
        :source-file="sourceFile"
      />
    </div>
  </div>
</template>

<script lang="ts" setup>
import TsSourceFileRenderer from '@/components/TsSourceFileRenderer.vue';
import { ref, computed } from 'vue';
import {
  createSourceFile,
  ScriptTarget,
} from 'typescript';

const sourceCode = ref('');

const sourceFile = computed(() => createSourceFile(
  'test.ts',
  sourceCode.value,
  ScriptTarget.ES2021,
  true,
));
</script>

<style scoped>
.editorContainer {
  width: 100%;
  height: 100%;
  display: grid;
  grid-template-columns: 1fr 10fr 1fr 10fr 1fr;
  grid-template-rows: 1fr 10fr 1fr;
}

.codeEditor {
  grid-column: 2 / 3;
  grid-row: 2 / 3;
}

.renderContainer {
  grid-column: 4 / 5;
  grid-row: 2 / 3;
}
</style>
