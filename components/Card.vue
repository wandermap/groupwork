<template>
  <div class="column">
    <div class="card">
      <header class="card-header">
        <p class="card-header-title has-text-grey">
          {{ title }}
        </p>
      </header>
      <slot />
      <div class="card-content">
        <div class="content has-text-centered">
          <!-- <b-icon :icon="icon" size="is-large" type="is-primary" /> -->
          {{ info }}
        </div>
      </div>
      <!-- <footer class="card-footer">
        <div class="card-footer-item">
          <span> </span>
        </div>
      </footer> -->
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    icon: {
      type: String,
      required: false,
    },
    info: {
      type: String,
      required: false,
    },
    rel: {
      type: String,
      required: false,
    },
  },
}
</script>
