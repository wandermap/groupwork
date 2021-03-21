<template>
  <section class="section">
    <h2 class="title is-3">
      宇宙開発プロジェクト <b-icon icon="rocket" size="is-large" />
    </h2>
    <div class="grid-3" style="column-gap: 10px; row-gap: 1em">
      <article
        v-for="(lesson, id) of lessons"
        :key="id"
        class="panel is-primary"
      >
        <p class="panel-heading">第{{ lesson.id }}回：{{ lesson.name }}</p>

        <nuxt-link to="lecture" class="panel-block is-active">
          <span class="panel-icon">
            <i class="fas fa-book" aria-hidden="true"></i>
          </span>
          動画レクチャー
        </nuxt-link>
        <nuxt-link to="check" class="panel-block is-active">
          <span class="panel-icon">
            <i class="fas fa-book" aria-hidden="true"></i>
          </span>
          確認問題
        </nuxt-link>
        <nuxt-link to="self-assessment" class="panel-block is-active">
          <span class="panel-icon">
            <i class="fas fa-book" aria-hidden="true"></i>
          </span>
          自己評価
        </nuxt-link>
        <nuxt-link to="group-assessment" class="panel-block is-active">
          <span class="panel-icon">
            <i class="fas fa-book" aria-hidden="true"></i>
          </span>
          グループメンバーの評価
        </nuxt-link>
      </article>
    </div>
  </section>
</template>

<style scoped>
.panel-block {
  background: white;
}
</style>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data() {
    return {
      lessons: [
        { id: 1, name: '目的を決めよう' },
        { id: 2, name: '設計図を書こう' },
        { id: 3, name: '必要な備品を整理しよう' },
        { id: 4, name: '役割分担を決めよう' },
        { id: 5, name: 'スケジュールを決めよう' },
        { id: 6, name: '開発①：土台作り' },
      ],
    }
  },
})
</script>
