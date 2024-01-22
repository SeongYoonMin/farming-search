<script lang="ts" setup>
interface ICategory {
  name: string;
  key: string;
  img: string;
  path: string;
}
const category = ref<ICategory[]>([
  {
    name: "NEXON",
    key: "nexon",
    img: "icons/nexon.png",
    path: "/nexon",
  },
  {
    name: "SMILEGATE",
    key: "smilegate",
    img: "icons/smilegate.png",
    path: "/smilegate",
  },
  {
    name: "NCSOFT",
    key: "ncsoft",
    img: "icons/ncsoft.png",
    path: "/ncsoft",
  },
  {
    name: "BLIZZARD",
    key: "blizzard",
    img: "icons/blizzard.png",
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
        class="items"
        :key="items.key"
        ><img :src="items.img" :alt="items.name" class="logo" />{{
          items.name
        }}</NuxtLink
      >
    </nav>
  </aside>
</template>

<style lang="scss" scoped>
#navigation {
  position: relative;
  background-color: #616161;
  box-sizing: border-box;
  padding: 16px 0;
  .list {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 40px;
    .items {
      position: relative;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 6px;
      transition: 0.4s all;
      width: 100%;
      padding: 0 16px;
      box-sizing: border-box;
      .logo {
        width: 48px;
        height: 48px;
        background-color: white;
        border-radius: 8px;
      }
      &::after {
        transition: 0.4s all;
        position: absolute;
        content: "";
        top: 50%;
        transform: translateY(-50%);
        left: 0;
        width: 4px;
        height: 10px;
        border-top-right-radius: 8px;
        border-bottom-right-radius: 8px;
        background-color: white;
      }
      color: white;
      &:hover {
        &::after {
          height: 30px;
        }
      }
      &.router-link-active {
        &::after {
          height: 90%;
        }
      }
    }
  }
}
</style>
