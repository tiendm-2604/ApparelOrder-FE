<template>
  <div id="about-us">
    <a-page-header class="content__header" title="会社情報" />

    <table class="about__info">
      <tr class="row" v-for="info in aboutInfos" :key="info.index">
        <th class="label">{{ info.label }}</th>
        <td class="info">{{ info.info }}</td>
      </tr>
    </table>

    <div class="about__button">
      <a href="/company-info-edit"><Button :buttonLabel="buttonLabel" /></a>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      aboutInfos: [
        { label: "会社名", info: "〇〇会社" },
        { label: "郵便番号", info: "123-4567" },
        { label: "住所", info: "東京都〜" },
        { label: "電話番号", info: "03-1234-5678" },
      ],

      buttonLabel: "編集",
    };
  },
};
</script>

<style lang="scss" scoped>
#about-us {
  width: 100%;

  .content__header {
    box-shadow: 0px 1px 2px rgba(0, 0, 0, 0.25);
    height: 11.8rem;
  }

  .about__info::v-deep {
    margin: 0px 2.4rem;
    width: 96%;

    .row {
      font-size: 1.6rem;

      &:nth-child(even) {
        background-color: #fafafa;
      }

      .label {
        padding: 1.6rem 0 1.6rem 7.2rem;
        width: 25rem;
        color: #303030;
      }

      .info {
        padding: 1.6rem;
        color: #888888;
      }
    }
  }

  .about__button {
    display: flex;
    justify-content: center;
    margin-top: 4.8rem;
  }
}
</style>