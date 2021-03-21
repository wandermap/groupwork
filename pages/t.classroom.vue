<template>
  <section class="section">
    <div class="is-size-4 has-text-weight-bold">クラス管理</div>
    <b-button type="is-success " @click="showModal = true">追加</b-button>
    <!-- カード -->
    <div class="grid is-mobile">
      <nuxt-link
        v-for="item in items"
        :key="item.id"
        to="t.member"
        class="card message is-success mx-2 my-2"
      >
        <div class="message-header">
          <p>{{ item.name }}</p>
          <button type="button" class="delete" @click="confirm" />
        </div>
        <div class="message-body" style="background: white">
          <b-icon :icon="item.icon" />
          **************
        </div>
      </nuxt-link>
    </div>

    <!-- モーダル -->
    <b-modal
      v-model="showModal"
      has-modal-card
      trap-focus
      aria-role="dialog"
      aria-label="Example Modal"
      aria-modal
    >
      <div class="modal-card" style="width: auto">
        <header class="modal-card-head">
          <p class="modal-card-title">クラス追加</p>
          <button type="button" class="delete" @click="showModal = false" />
        </header>

        <section class="modal-card-body">
          <b-field label="クラス名">
            <b-input v-model="name" type="text" class="center" placeholder="A">
            </b-input>
          </b-field>

          <b-field label="備考">
            <b-input v-model="note" type="textarea" placeholder=""> </b-input>
          </b-field>
        </section>

        <footer class="modal-card-foot">
          <b-button label="キャンセル" @click="showModal = false" />
          <b-button label="登録" type="is-success" @click="addClass" />
        </footer>
      </div>
    </b-modal>
  </section>
</template>

<script lang="ts">
import Vue from 'vue'
import Buefy from 'buefy'
export default Vue.extend({
  layout: 'teacher',
  data() {
    return {
      items: [
        { id: 1, name: '3-A組', icon: 'google-classroom ' },
        { id: 2, name: '3-B組', icon: 'google-classroom ' },
        { id: 3, name: '3-C組', icon: 'google-classroom ' },
        { id: 4, name: '3-D組', icon: 'google-classroom ' },
        { id: 5, name: '2-A組', icon: 'google-classroom ' },
        { id: 6, name: '2-B組', icon: 'google-classroom ' },
        { id: 7, name: '2-C組', icon: 'google-classroom ' },
        { id: 8, name: '2-D組', icon: 'google-classroom ' },
        { id: 9, name: '1-A組', icon: 'google-classroom ' },
        { id: 10, name: '1-B組', icon: 'google-classroom ' },
        { id: 11, name: '1-C組', icon: 'google-classroom ' },
        { id: 12, name: '1-D組', icon: 'google-classroom ' },
      ],
      showModal: false,
      name: '',
      note: '',
    }
  },
  methods: {
    addClass() {
      const len = this.items.length + 1
      this.items.push({ id: len, name: this.name, icon: 'google-classroom ' })
      this.name = ''
      this.showModal = false
    },

    confirm(): any {
      this.$buefy.dialog.confirm({
        message: 'クラス' + this.name + 'を削除しますか？',
        onConfirm: () => this.$buefy.toast.open('作成しました'),
      })
    },
  },
})
</script>

<style scoped>
.card {
  border: solid thin lightgray;
}
</style>
