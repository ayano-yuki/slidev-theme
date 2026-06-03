<template>
  <span class="theme-badge"><slot /></span>
</template>

<style scoped>
.theme-badge {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 0.35rem 0.75rem;
  border-radius: 999px;
  background: rgba(96, 165, 250, 0.18);
  color: #bfdbfe;
  font-size: 0.9rem;
}
</style>
