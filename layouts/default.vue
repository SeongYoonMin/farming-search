<script setup lang="ts"></script>

<template>
  <main id="default">
    <LayoutNavbar />
    <div id="main">
      <slot />
    </div>
  </main>
</template>

<style lang="scss" scoped>
#default {
  display: flex;
  align-items: center;
  justify-content: center;
  #navigation {
    width: 100%;
    max-width: 300px;
  }
  #main {
    flex: 1 1 0%;
  }
}
</style>
