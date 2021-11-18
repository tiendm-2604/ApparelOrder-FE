<template>
  <div id="company-info-edit">
    <table class="info__edit">
      <tr class="row" v-for="info in aboutInfos" :key="info.index">
        <th class="label">{{ info.label }} <span class="red__star">*</span></th>
        <td class="info">
          <a-input class="info__input" v-model="info.info" />
        </td>
      </tr>
    </table>

    <div class="info__buttons">
      <Button :buttonLabel="buttonLabel1" />
      <Button style="margin-left: 2rem" :buttonLabel="buttonLabel2" />
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

      buttonLabel1: "キャンセル",
      buttonLabel2: "編集",
    };
  },
};
</script>

<style lang="scss" scoped>
#company-info-edit {
  width: 100%;

  .info__edit::v-deep {
    margin: 0px 2.4rem;
    width: 96%;

    .row {
      font-size: 1.6rem;
      border-bottom: 1px solid #f0f0f0;

      .label {
        padding: 1.6rem 0 1.6rem 7.2rem;
        width: 25rem;
        color: #303030;

        .red__star {
          color: #d47273;
        }
      }

      .info {
        padding: 1.6rem;
        color: #888888;

        .info__input {
          width: 26rem;
          color: #888888;
        }
      }
    }
  }

  .info__buttons {
    display: flex;
    justify-content: center;
    margin-top: 4.8rem;
  }
}
</style>