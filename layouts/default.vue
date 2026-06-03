<template>
  <section class="theme-shell">
    <div class="theme-frame">
      <slot />
    </div>
  </section>
</template>

<style scoped>
.theme-shell {
  min-height: 100vh;
  background: linear-gradient(180deg, #101827 0%, #1e293b 100%);
  color: #f8fafc;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 4rem 1.5rem;
}

.theme-frame {
  width: min(1100px, 100%);
  background: rgba(15, 23, 42, 0.92);
  border: 1px solid rgba(148, 163, 184, 0.2);
  border-radius: 32px;
  box-shadow: 0 30px 80px rgba(15, 23, 42, 0.35);
  overflow: hidden;
}
</style>
