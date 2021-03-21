<template>
  <div>
    <link
      href="https://use.fontawesome.com/releases/v5.6.1/css/all.css"
      rel="stylesheet"
    />
    <b-navbar class="is-success" fixed-top>
      <template #brand>
        <b-navbar-item tag="router-link" :to="{ path: '/' }">
          <b>グループワーク</b>
        </b-navbar-item>
      </template>
      <template #start>
        <b-navbar-item>
          <nuxt-link to="/" class="button">生徒 </nuxt-link>
        </b-navbar-item>
        <b-navbar-item>
          <nuxt-link to="t.classroom" class="button">教師 </nuxt-link>
        </b-navbar-item>
      </template>

      <template #end>
        <b-navbar-item tag="div">
          <div class="buttons">
            <a class="button is-light"> 会員登録 </a>
            <a class="button is-light"> ログイン </a>
          </div>
        </b-navbar-item>
      </template>
    </b-navbar>

    <section class="main-content columns has-background-success-light">
      <aside class="column is-2 section">
        <ul class="menu-list">
          <li v-for="(item, key) of items" :key="key">
            <nuxt-link :to="item.to" exact-active-class="is-active">
              <b-icon :icon="item.icon" /> {{ item.title }}
            </nuxt-link>
          </li>
        </ul>
      </aside>

      <div class="container column is-10">
        <nuxt />
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          title: 'クラス選択',
          icon: 'home',
          to: { name: 't.classroom' },
        },
        {
          title: 'グループ選択',
          icon: 'home',
          to: { name: 't.member' },
        },
        {
          title: 'グループワーク',
          icon: 'home',
          to: { name: 't.groupwork' },
        },
      ],
    }
  },
}
</script>
<style>
.main-content {
  min-height: calc(100vh - 50px);
}

/* .menu-list a.is-active {
  background-color: rgb(2, 134, 90);
  color: #fff;
} */
</style>
