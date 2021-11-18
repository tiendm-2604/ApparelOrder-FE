<template>
  <div id="sidebar">
    <div class="sidebar">
      <a-menu
        class="menu"
        :default-selected-keys="['1']"
        mode="inline"
        theme="light"
        :inline-collapsed="collapsed"
      >
        <template v-for="menu in menus">
          <a-menu-item
            class="menu__item"
            v-if="!menu.subMenus"
            :key="menu.index"
          >
            <a-icon type="bars" /> <span>{{ menu.name }}</span>
          </a-menu-item>

          <a-sub-menu class="subMenu__item" v-else :key="menu.index">
            <span slot="title">
              <a-icon type="bars" /> <span>{{ menu.name }}</span></span
            >
            <a-menu-item v-for="subMenu in menu.subMenus" :key="subMenu.index">
              {{ subMenu }}</a-menu-item
            >
          </a-sub-menu>
        </template>
      </a-menu>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      menus: [
        { name: "アイテム一覧" },
        { name: "ユーザー管理", subMenus: ["Option 5", "Option 6"] },
        { name: "会社情報" },
        { name: "ヘルプ", subMenus: ["Option 5", "Option 6"] },
      ],
    };
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
#sidebar {
  .sidebar {
    width: 24.4rem;
    font-size: 1.4rem;

    .menu {
      padding-top: 4rem;
      height: calc(100vh - 6.8rem);
      position: relative;
    }

    .gray-color {
      color: #495570;
    }

    .menu__item:hover {
      @extend .gray-color;
    }

    .ant-menu:not(.ant-menu-horizontal) .ant-menu-item-selected {
      &::after {
        border-right: 3px solid #9b8c6f;
      }

      @extend .gray-color;
      background-color: #d8ce9e;
    }

    .ant-menu-submenu {
      &-selected {
        @extend .gray-color;
      }

      &-title:hover {
        @extend .gray-color;
      }
    }
  }
}
</style>