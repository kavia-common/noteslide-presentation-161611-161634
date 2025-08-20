<script setup lang="ts">
/**
 * PUBLIC_INTERFACE
 * AppShell layout component for slides wanting a header + sidebar style.
 * Use in frontmatter: layout: app-shell
 */
defineProps<{}>
</script>

<template>
  <div class="app-shell">
    <header class="brand-header">
      <div class="brand-logo" aria-hidden="true" />
      <div class="brand-title">NoteSlide</div>
      <HeaderControls />
    </header>
    <aside class="app-sidebar">
      <div class="text-xs uppercase opacity-60 mb-2">Slides</div>
      <Toc minDepth="1" maxDepth="2" />
    </aside>
    <main class="app-main">
      <slot />
    </main>
  </div>
</template>

<style scoped>
.app-shell {
  display: grid;
  grid-template-columns: 0px 1fr;
  grid-template-rows: 56px 1fr;
}
@media (min-width: 640px) {
  .app-shell {
    grid-template-columns: 16rem 1fr;
  }
}
.brand-header {
  grid-column: 1 / -1;
}
.app-sidebar {
  display: none;
  padding: 12px;
  border-right: 1px solid rgba(0,0,0,0.06);
  overflow: auto;
}
@media (min-width: 640px) {
  .app-sidebar {
    display: block;
    grid-row: 2 / 3;
  }
}
.app-main {
  grid-row: 2 / 3;
  padding: 16px;
}
</style>
