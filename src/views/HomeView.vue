<template>
  <div class="editorContainer">
    <textarea
      class="codeEditor"
      aria-label="Code editor"
    />
  </div>
</template>

<script lang="ts" setup>
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
</style>
