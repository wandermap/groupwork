<template>
  <section class="section">
    <h2 class="title is-3">
      メンバー評価 <b-icon icon="rocket" size="is-large" />
    </h2>
    <section>
      <div v-for="men in members" :key="men.id" class="mb-5">
        {{ men.name }}
        <b-tabs type="is-toggle" class="has-background-white">
          <b-tab-item v-for="quiz in questions" :key="quiz.id" :label="quiz.q">
            <!-- Q -->
            <article class="message is-info">
              <div class="message-body">
                <div><b>Q1:自主性</b></div>
                <p>{{ men.name }}は頑張りましたか？</p>
              </div>
            </article>
            <!-- A -->
            <b-field>
              <b-radio v-model="quiz.radio1" type="is-info" native-value="A">
                すんごい頑張った
              </b-radio>
            </b-field>
            <b-field>
              <b-radio v-model="quiz.radio1" type="is-info" native-value="B">
                割といい感じに頑張った
              </b-radio>
            </b-field>
            <b-field>
              <b-radio v-model="quiz.radio1" type="is-info" native-value="C">
                そこはなとなく頑張った気がする
              </b-radio>
            </b-field>
            <section class="has-background-white mt-5 p-2">
              <b-field label="コメント">
                <b-input maxlength="200" type="textarea"></b-input>
              </b-field>
            </section>
          </b-tab-item>
        </b-tabs>
      </div>
    </section>
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
        { id: 1, name: 'サトウ' },
        { id: 2, name: 'スズキ' },
        { id: 3, name: 'タカハシ' },
      ],
    }
  },
})
</script>
