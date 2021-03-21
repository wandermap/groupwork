<template>
  <section class="section">
    <h2 class="title is-3">
      グループワーク <b-icon icon="rocket" size="is-large" />
    </h2>
    <b-message
      title="グループワークの課題"
      type="is-info"
      :closable="false"
      has-icon
      style="max-width: 800px"
    >
      <p>ここからがグループワークの本番です</p>
      <p>
        <b>「どんな目的の宇宙開発をしたいか」</b
        >について、グループで話し合って決めてください
      </p>
    </b-message>
    <p>※グループワークが終了したら、次のボタンから評価に進んでください</p>
    <nuxt-link to="self-assessment" class="button">自己評価へ進む</nuxt-link>
  </section>
</template>

<style scoped>
.panel-block {
  background: white;
}
</style>
