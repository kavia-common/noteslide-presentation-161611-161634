<script setup lang="ts">
/**
 * PUBLIC_INTERFACE
 * A simple reusable header control group for navigation and theme toggle.
 * Emits no events; directly uses the global $slidev and $page composables available in Slidev context.
 */
</script>

<template>
  <div class="brand-controls">
    <button class="control-btn" title="Previous" @click="$slidev.nav.prev()">
      <carbon:chevron-left /> Prev
    </button>
    <button class="control-btn" title="Next" @click="$slidev.nav.next()">
      Next <carbon:chevron-right />
    </button>
    <button class="control-btn" title="Toggle Dark" @click="$page.toggleDark()">
      <carbon:moon /> / <carbon:sun />
    </button>
    <button class="control-btn" title="Open in Editor" @click="$slidev.nav.openInEditor">
      <carbon:edit />
    </button>
  </div>
</template>

<style scoped>
/* Scoped to maintain minimalism, uses global variables defined in slides.md */
.brand-controls {
  margin-left: auto;
  display: flex;
  gap: 8px;
}
.control-btn {
  border: 1px solid rgba(0,0,0,0.08);
  padding: 6px 10px;
  border-radius: 8px;
  background: white;
}
:global(.dark) .control-btn {
  background: #111214;
  border-color: rgba(255,255,255,0.08);
  color: #eaeaea;
}
</style>
