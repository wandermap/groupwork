<template>
  <section class="section">
    <div class="is-size-4 has-text-weight-bold">メンバー管理 > 3-A組</div>
    <section>
      <b-tabs type="is-toggle">
        <b-tab-item label="宇宙開発コース">
          <div class="grid-3">
            <div v-for="(group, id) of groups" :key="id">
              <div class="card m-3">
                <header
                  class="card-header is-size-3 p-2"
                  style="justify-content: space-between"
                >
                  <div>
                    <b>{{ group.name }}</b>
                  </div>
                  <b-button
                    type="is-success "
                    class="mt-2"
                    @click="showModal = true"
                    >追加</b-button
                  >
                </header>
                <b-table
                  :data="data"
                  :striped="true"
                  :narrowed="true"
                  :hoverable="true"
                  :mobile-cards="true"
                >
                  <b-table-column
                    field="id"
                    label="ID"
                    width="40"
                    numeric
                    header-class="has-background-success-light"
                    v-slot="props"
                  >
                    {{ props.row.id }}
                  </b-table-column>

                  <b-table-column
                    field="last_name"
                    label="姓"
                    header-class="has-background-success-light"
                    v-slot="props"
                  >
                    {{ props.row.last_name }}
                  </b-table-column>

                  <b-table-column
                    field="first_name"
                    label="名"
                    header-class="has-background-success-light"
                    v-slot="props"
                  >
                    {{ props.row.first_name }}
                  </b-table-column>

                  <b-table-column
                    label="Gender"
                    header-class="has-background-success-light"
                    v-slot="props"
                  >
                    <span>
                      <b-icon
                        pack="fas"
                        :icon="props.row.gender === 'Male' ? 'mars' : 'venus'"
                      >
                      </b-icon>
                      {{ props.row.gender }}
                    </span>
                  </b-table-column>

                  <b-table-column
                    field="Edit"
                    label="Edit"
                    header-class="has-background-success-light"
                    v-slot="props"
                  >
                    <b-button
                      class="fas fa-edit"
                      v-model="props.row.id"
                      @click="showModal = true"
                    ></b-button>
                  </b-table-column>
                </b-table>
              </div>
            </div>
          </div>
        </b-tab-item>
        <b-tab-item label="模擬裁判コース">
          <div class="grid-3">
            <div v-for="(group, id) of groups2" :key="id">
              <div class="card m-3">
                <header
                  class="card-header is-size-3 p-2"
                  style="justify-content: space-between"
                >
                  <div>
                    <b>{{ group.name }}班</b>
                  </div>
                  <b-button
                    type="is-success "
                    class="mt-2"
                    @click="showModal = true"
                    >追加</b-button
                  >
                </header>
                <b-table
                  :data="data2"
                  :striped="true"
                  :narrowed="true"
                  :hoverable="true"
                  :mobile-cards="true"
                >
                  <b-table-column
                    field="id"
                    label="ID"
                    width="40"
                    numeric
                    header-class="has-background-success-light"
                    v-slot="props"
                  >
                    {{ props.row.id }}
                  </b-table-column>

                  <b-table-column
                    field="last_name"
                    label="姓"
                    header-class="has-background-success-light"
                    v-slot="props"
                  >
                    {{ props.row.last_name }}
                  </b-table-column>

                  <b-table-column
                    field="first_name"
                    label="名"
                    header-class="has-background-success-light"
                    v-slot="props"
                  >
                    {{ props.row.first_name }}
                  </b-table-column>

                  <b-table-column
                    label="Gender"
                    header-class="has-background-success-light"
                    v-slot="props"
                  >
                    <span>
                      <b-icon
                        pack="fas"
                        :icon="props.row.gender === 'Male' ? 'mars' : 'venus'"
                      >
                      </b-icon>
                      {{ props.row.gender }}
                    </span>
                  </b-table-column>

                  <b-table-column
                    field="Edit"
                    label="Edit"
                    header-class="has-background-success-light"
                    v-slot="props"
                  >
                    <b-button
                      class="fas fa-edit"
                      v-model="props.row.id"
                      @click="showModal = true"
                    ></b-button>
                  </b-table-column>
                </b-table>
              </div>
            </div>
          </div>
        </b-tab-item>
      </b-tabs>
    </section>

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
          <p class="modal-card-title">メンバー追加</p>
          <button type="button" class="delete" @click="showModal = false" />
        </header>

        <section class="modal-card-body">
          <b-field label="姓">
            <b-input
              v-model="last_name"
              type="text"
              class="center"
              placeholder="A"
            >
            </b-input>
          </b-field>

          <b-field label="名">
            <b-input
              v-model="fast_name"
              type="text"
              class="center"
              placeholder="A"
            >
            </b-input>
          </b-field>

          <div class="block">
            <b-radio v-model="radio" name="gender" native-value="Male">
              Male
            </b-radio>
            <b-radio v-model="radio" name="gender" native-value="Female">
              Female
            </b-radio>
          </div>
        </section>

        <footer class="modal-card-foot">
          <b-button label="キャンセル" @click="showModal = false" />
          <b-button label="登録" type="is-success" @click="addMember" />
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
      groups: [
        { id: 1, name: 'A班' },
        { id: 2, name: 'B班' },
        { id: 3, name: 'C班' },
        { id: 4, name: 'D班' },
        { id: 5, name: 'E班' },
        { id: 6, name: 'F班' },
      ],
      groups2: [
        { id: 1, name: '弁護士' },
        { id: 2, name: '検事' },
        { id: 3, name: '裁判員' },
      ],
      data: [
        {
          id: 1,
          first_name: 'Jesse',
          last_name: 'Simmons',
          date: '2016-10-15 13:43:27',
          gender: 'Male',
        },
        {
          id: 2,
          first_name: 'John',
          last_name: 'Jacobs',
          date: '2016-12-15 06:00:53',
          gender: 'Male',
        },
        {
          id: 3,
          first_name: 'Tina',
          last_name: 'Gilbert',
          date: '2016-04-26 06:26:28',
          gender: 'Female',
        },
        {
          id: 4,
          first_name: 'Clarence',
          last_name: 'Flores',
          date: '2016-04-10 10:28:46',
          gender: 'Male',
        },
        {
          id: 5,
          first_name: 'Anne',
          last_name: 'Lee',
          date: '2016-12-06 14:38:38',
          gender: 'Female',
        },
      ],
      data2: [
        {
          id: 1,
          first_name: 'Jesse',
          last_name: 'Simmons',
          date: '2016-10-15 13:43:27',
          gender: 'Male',
        },
        {
          id: 2,
          first_name: 'John',
          last_name: 'Jacobs',
          date: '2016-12-15 06:00:53',
          gender: 'Male',
        },
        {
          id: 3,
          first_name: 'Tina',
          last_name: 'Gilbert',
          date: '2016-04-26 06:26:28',
          gender: 'Female',
        },
        {
          id: 4,
          first_name: 'Clarence',
          last_name: 'Flores',
          date: '2016-04-10 10:28:46',
          gender: 'Male',
        },
        {
          id: 5,
          first_name: 'Anne',
          last_name: 'Lee',
          date: '2016-12-06 14:38:38',
          gender: 'Female',
        },
        {
          id: 6,
          first_name: 'Anne',
          last_name: 'Lee',
          date: '2016-12-06 14:38:38',
          gender: 'Female',
        },
        {
          id: 7,
          first_name: 'Anne',
          last_name: 'Lee',
          date: '2016-12-06 14:38:38',
          gender: 'Female',
        },
        {
          id: 8,
          first_name: 'Anne',
          last_name: 'Lee',
          date: '2016-12-06 14:38:38',
          gender: 'Female',
        },
      ],
      showModal: false,
      name: '',
      fast_name: '',
      last_name: '',
      note: '',
      radio: 'Male',
    }
  },
  methods: {
    addMember() {
      const len = this.data.length + 1
      this.data.push({
        id: len,
        first_name: this.fast_name,
        last_name: this.last_name,
        date: '2016-10-15 13:43:27',
        gender: this.radio,
      })
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

.tabs li {
  background: white !important;
}
</style>
