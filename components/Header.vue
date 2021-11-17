<template>
  <div id="header">
    <a-page-header class="title" title="GOOD VIBES ONLY." />

    <a-dropdown class="dropdown" :trigger="['click']">
      <a class="ant-dropdown-link" @click="(e) => e.preventDefault()">
        山田 太郎 <a-icon class="arrow-icon" type="caret-down" />
      </a>
      <a-menu slot="overlay">
        <a-menu-item key="0">
          <a href="http://www.alipay.com/">1st menu item</a>
        </a-menu-item>
        <a-menu-item key="1">
          <a href="http://www.taobao.com/">2nd menu item</a>
        </a-menu-item>
        <a-menu-divider />
        <a-menu-item key="3"> 3rd menu item </a-menu-item>
      </a-menu>
    </a-dropdown>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
#header {
  background-color: #596789;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 4px solid #beb68d;

  .font-white {
    font-size: 1.8rem;
    color: white;
  }

  .title::v-deep {
    .ant-page-header-heading-title {
      @extend .font-white;
    }
  }

  .dropdown {
    @extend .font-white;

    margin-right: 2rem;

    .arrow-icon {
      margin-left: 1rem;
    }
  }
}
</style>