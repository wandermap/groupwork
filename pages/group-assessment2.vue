<template>
  <section class="section">
    <h2 class="title is-3">
      メンバー評価：別イメージ <b-icon icon="rocket" size="is-large" />
    </h2>
    <section class="has-background-white">
      <b-tabs type="is-toggle">
        <b-tab-item v-for="men in members" :key="men.id" :label="men.name">
          <!-- ラベル -->
          <section class="grid-4 has-background-primary-light">
            <div>質問</div>
            <div style="text-align: center">ちょっと良い</div>
            <div style="text-align: center">まあまあ良い</div>
            <div style="text-align: center">とても良い</div>
          </section>

          <!-- 評価 -->
          <section v-for="quiz in questions" :key="quiz.id" class="grid-4 p-1">
            <div>
              <span style="color: red">{{ men.name }}</span> の{{
                quiz.q
              }}は、どうでしたか？
            </div>
            <div style="text-align: center">
              <b-radio v-model="quiz.radio1" type="is-info" native-value="A">
              </b-radio>
            </div>
            <div style="text-align: center">
              <b-radio v-model="quiz.radio1" type="is-info" native-value="B">
              </b-radio>
            </div>
            <div style="text-align: center">
              <b-radio v-model="quiz.radio1" type="is-info" native-value="C">
              </b-radio>
            </div>
          </section>
        </b-tab-item>
      </b-tabs>
    </section>
    <b-button type="is-warning" class="mt-3" @click="alert"
      >評価入力を完了する</b-button
    >
  </section>
</template>

<style scoped>
.panel-block {
  background: white;
}
.grid-4 {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr 1fr;
}
</style>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data() {
    return {
      radio1: 'A',
      questions: [
        { id: 1, q: 'Q1:〇〇性' },
        { id: 2, q: 'Q2:〇〇性' },
        { id: 3, q: 'Q3:〇〇性' },
        { id: 4, q: 'Q4:〇〇性' },
        { id: 5, q: 'Q5:〇〇性' },
        { id: 6, q: 'Q6:〇〇性' },
      ],
      members: [
        { id: 0, name: '自分' },
        { id: 1, name: 'サトウ' },
        { id: 2, name: 'スズキ' },
        { id: 3, name: 'タカハシ' },
      ],
    }
  },
  methods: {
    alert() {
      this.$buefy.dialog.confirm({
        message: 'お疲れさまでした',
        type: 'is-warning',
        confirmText: '終了します',
        cancelText: 'キャンセル',
        hasIcon: false,
        onConfirm: () => this.$router.push('/'),
      })
    },
  },
})
</script>
