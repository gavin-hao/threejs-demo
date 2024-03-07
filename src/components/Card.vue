<template>
  <div class="card">
    <div class="card-body">
      <slot></slot>
    </div>
  </div>
</template>
<style lang="scss" scoped>
.card {
  --padding--card--dense: 16px;
  --border-radius--card--dense: 4px;
  --border-radius: 4px;
  --border-radius--card: 4px;
  --card--border-radius: var(--border-radius--card);
  --card--padding: 24px;
  --card--cancel-padding: calc(var(--card--padding) * -1);
  --card--gap: var(--card--padding);
  --card--width: calc(75ch + var(--padding--card--dense) * 2);
  display: flex;
  max-inline-size: var(--card--width);
  block-size: min-content;
  max-block-size: min-content;
  overflow: hidden;
  background-color: var(--theme-background-container);
  border-radius: var(--border-radius--card);
  transition: background-color 0.33s ease;
  .card-body {
    flex-grow: 1;
    width: 100%;
    padding: var(--card--padding);
    padding-inline-end: max(var(--app-size--3x), var(--card--padding));
  }
}
</style>
