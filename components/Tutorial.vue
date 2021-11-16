<template>
  <a-descriptions title="User Info" layout="horizontal" :column="1" bordered>
    <a-descriptions-item label="ユーザー名_漢字">
      山田太郎
    </a-descriptions-item>
    <a-descriptions-item label="ユーザー名_フリガナ">
      ヤマダタロウ
    </a-descriptions-item>
    <a-descriptions-item label="メールアドレス">
      aaa@ccc.jp
    </a-descriptions-item>
    <a-descriptions-item label="部署"> MD部 </a-descriptions-item>
    <a-descriptions-item label="ステータス"> 利用中 </a-descriptions-item>
    <a-descriptions-item label="権限">
      <div
        class="abc"
      >
        一般 <a-button>Default</a-button>
      </div>
    </a-descriptions-item>
    <a-descriptions-item label="電話番号"> 03-1234-5678 </a-descriptions-item>
    <a-descriptions-item label="アクセス可能ブランド">
      ブランドA
    </a-descriptions-item>
  </a-descriptions>
</template>
<style>
.abc {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.ant-descriptions-bordered .ant-descriptions-view {
  border: none;
}
th.ant-descriptions-item-label.ant-descriptions-item-colon {
  width: 220px;
  background-color: transparent;
  border-right: 0;
}
tr.ant-descriptions-row:nth-child(even) {
  background: #fafafa;
}
</style>
