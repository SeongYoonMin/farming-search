<script lang="ts" setup>
interface ICategory {
  name: string;
  key: string;
  path: string;
}
const category = ref<ICategory[]>([
  {
    name: "NEXON",
    key: "nexon",
    path: "/nexon",
  },
  {
    name: "SMILEGATE",
    key: "smilegate",
    path: "/smileagte",
  },
  {
    name: "NCSOFT",
    key: "ncsoft",
    path: "/ncsoft",
  },
  {
    name: "BLIZZARD",
    key: "blizzard",
    path: "/blizzard",
  },
]);
</script>

<template>
  <aside id="navigation">
    <nav class="list">
      <NuxtLink
        :to="items.path"
        v-for="items in category"
        class="itmes"
        :key="items.key"
        >{{ items.name }}</NuxtLink
      >
    </nav>
  </aside>
</template>

<style lang="scss" scoped>
#navigation {
  position: relative;
  .list {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: center;
  }
}
</style>
