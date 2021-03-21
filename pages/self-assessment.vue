<template>
  <section class="section">
    <h2 class="title is-3">
      自己評価 <b-icon icon="rocket" size="is-large" />
    </h2>
    <section class="has-background-white">
      <b-tabs type="is-toggle">
        <b-tab-item label="Q1:自主性">
          <!-- Q -->
          <article class="message is-info">
            <div class="message-body">
              <div><b>Q1:自主性</b></div>
              <p>あなたは頑張りましたか？</p>
            </div>
          </article>
          <!-- A -->
          <b-field>
            <b-radio v-model="radio1" type="is-info" native-value="A">
              すんごい頑張った
            </b-radio>
          </b-field>
          <b-field>
            <b-radio v-model="radio1" type="is-info" native-value="B">
              割といい感じに頑張った
            </b-radio>
          </b-field>
          <b-field>
            <b-radio v-model="radio1" type="is-info" native-value="C">
              そこはなとなく頑張った気がする
            </b-radio>
          </b-field>
        </b-tab-item>

        <b-tab-item label="Q2:〇〇性">
          <!-- Q -->
          <article class="message is-info">
            <div class="message-body">
              <div><b>Q1:自主性</b></div>
              <p>あなたは頑張りましたか？</p>
            </div>
          </article>
          <!-- A -->
          <b-field>
            <b-radio v-model="radio1" type="is-info" native-value="A">
              すんごい頑張った
            </b-radio>
          </b-field>
          <b-field>
            <b-radio v-model="radio1" type="is-info" native-value="B">
              割といい感じに頑張った
            </b-radio>
          </b-field>
          <b-field>
            <b-radio v-model="radio1" type="is-info" native-value="C">
              そこはなとなく頑張った気がする
            </b-radio>
          </b-field>
        </b-tab-item>

        <b-tab-item label="Q3:〇〇性">
          <!-- Q -->
          <article class="message is-info">
            <div class="message-body">
              <div><b>Q1:自主性</b></div>
              <p>あなたは頑張りましたか？</p>
            </div>
          </article>
          <!-- A -->
          <b-field>
            <b-radio v-model="radio1" type="is-info" native-value="A">
              すんごい頑張った
            </b-radio>
          </b-field>
          <b-field>
            <b-radio v-model="radio1" type="is-info" native-value="B">
              割といい感じに頑張った
            </b-radio>
          </b-field>
          <b-field>
            <b-radio v-model="radio1" type="is-info" native-value="C">
              そこはなとなく頑張った気がする
            </b-radio>
          </b-field>
        </b-tab-item>

        <b-tab-item label="Q4:〇〇性">
          <!-- Q -->
          <article class="message is-info">
            <div class="message-body">
              <div><b>Q1:自主性</b></div>
              <p>あなたは頑張りましたか？</p>
            </div>
          </article>
          <!-- A -->
          <b-field>
            <b-radio v-model="radio1" type="is-info" native-value="A">
              すんごい頑張った
            </b-radio>
          </b-field>
          <b-field>
            <b-radio v-model="radio1" type="is-info" native-value="B">
              割といい感じに頑張った
            </b-radio>
          </b-field>
          <b-field>
            <b-radio v-model="radio1" type="is-info" native-value="C">
              そこはなとなく頑張った気がする
            </b-radio>
          </b-field>
        </b-tab-item>

        <b-tab-item label="Q5:〇〇性">
          <!-- Q -->
          <article class="message is-info">
            <div class="message-body">
              <div><b>Q1:自主性</b></div>
              <p>あなたは頑張りましたか？</p>
            </div>
          </article>
          <!-- A -->
          <b-field>
            <b-radio v-model="radio1" type="is-info" native-value="A">
              すんごい頑張った
            </b-radio>
          </b-field>
          <b-field>
            <b-radio v-model="radio1" type="is-info" native-value="B">
              割といい感じに頑張った
            </b-radio>
          </b-field>
          <b-field>
            <b-radio v-model="radio1" type="is-info" native-value="C">
              そこはなとなく頑張った気がする
            </b-radio>
          </b-field>
        </b-tab-item>

        <b-tab-item label="Q6:〇〇性">
          <!-- Q -->
          <article class="message is-info">
            <div class="message-body">
              <div><b>Q1:自主性</b></div>
              <p>あなたは頑張りましたか？</p>
            </div>
          </article>
          <!-- A -->
          <b-field>
            <b-radio v-model="radio1" type="is-info" native-value="A">
              すんごい頑張った
            </b-radio>
          </b-field>
          <b-field>
            <b-radio v-model="radio1" type="is-info" native-value="B">
              割といい感じに頑張った
            </b-radio>
          </b-field>
          <b-field>
            <b-radio v-model="radio1" type="is-info" native-value="C">
              そこはなとなく頑張った気がする
            </b-radio>
          </b-field>
        </b-tab-item>
      </b-tabs>
    </section>
    <section class="has-background-white mt-5 p-2">
      <b-field label="コメント">
        <b-input maxlength="200" type="textarea"></b-input>
      </b-field>
    </section>
    <nuxt-link to="group-assessment" class="button mt-3"
      >メンバー評価へ進む</nuxt-link
    >
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
    }
  },
})
</script>
