<template>
  <section class="section">
    <h2 class="title is-3">
      コース選択 <b-icon icon="rocket" size="is-large" />
    </h2>
    <div class="columns is-mobile">
      <card title="宇宙開発" info="ロケットを作ろう" rel="#">
        <nuxt-link to="lesson">
          <img src="~/static/space.jpg" alt="" />
        </nuxt-link>
      </card>

      <card title="調理実習" info="カレーを作ろう" rel="#">
        <nuxt-link to="lesson">
          <img src="~/static/curryruce.png" alt="" style="height: 130px" />
        </nuxt-link>
      </card>

      <card title="模擬裁判" info="法と戦おう" rel="#">
        <nuxt-link to="lesson">
          <img src="~/static/saiban.png" alt="" />
        </nuxt-link>
      </card>

      <card title="宇宙開発" info="ロケットを作ろう" rel="#">
        <nuxt-link to="lesson">
          <img src="~/static/space.jpg" alt="" />
        </nuxt-link>
      </card>
    </div>
  </section>
</template>

<script>
import Card from '~/components/Card'

export default {
  layout: 'primary',
  name: 'HomePage',
  rel: '',
  components: {
    Card,
  },
}
</script>
