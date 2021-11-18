<template>
  <div id="sidebar">
    <div class="sidebar">
      <a-menu
        class="menu"
        :default-selected-keys="['1']"
        mode="inline"
        theme="light"
      >
        <template v-for="menu in menus">
          <a-menu-item
            class="menu__item"
            v-if="!menu.subMenus"
            :key="menu.index"
          >
            <div class="center">
              <img class="icon" :src="menu.icon" alt="icon" />
              <span>{{ menu.name }}</span>
            </div>
          </a-menu-item>

          <a-sub-menu class="subMenu__item" v-else :key="menu.index">
            <span class="center" slot="title">
              <img class="icon" :src="menu.icon" alt="icon" />
              <span>{{ menu.name }}</span></span
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
        { name: "アイテム一覧", icon: "logos/Vector4.svg" },
        {
          name: "ユーザー管理",
          subMenus: ["Option 5", "Option 6"],
          icon: "logos/Vector3.svg",
        },
        { name: "会社情報", icon: "logos/Vector2.svg" },
        {
          name: "ヘルプ",
          subMenus: ["Option 5", "Option 6"],
          icon: "logos/Vector1.svg",
        },
      ],
    };
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
#sidebar {
  .sidebar::v-deep {
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

    .ant-menu-item:hover {
      @extend .gray-color;
      background-color: white;
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

        .ant-menu-submenu-arrow::before,
        .ant-menu-submenu-arrow::after {
          background: #495570;
        }
      }
    }

    .icon {
      transform: scale(1.25);
      margin-right: 1.7rem;
    }

    .center {
      display: flex;
      align-items: center;
    }
  }
}
</style>