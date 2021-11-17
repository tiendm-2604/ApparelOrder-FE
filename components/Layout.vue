<template>
  <div id="layout">
    <Header />

    <div class="content">
      <SideBar />

      <Nuxt />
    </div>
  </div>
</template>

<script></script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Noto+Sans+JP&display=swap");

#layout {
  font-family: "Noto Sans JP", sans-serif;

  .content {
    display: flex;
  }
}

html {
  font-size: 62.5%;
}
</style>