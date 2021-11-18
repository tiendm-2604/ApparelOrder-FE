<template>
  <a-button class="button"> {{ buttonLabel }} </a-button>
</template>

<script>
export default {
  props: ["buttonLabel"],
};
</script>

<style lang="scss" scoped>
.button {
  background-color: #9b8c6f;
  color: white;
  display: block;
  width: 24rem;
  height: 4.8rem;

  &:hover {
    color: #9b8c6f;
    background-color: white;
    border-color: #9b8c6f;
  }
}
</style>