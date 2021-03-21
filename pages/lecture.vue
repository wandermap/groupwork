<template>
  <section class="section">
    <h2 class="title is-3">
      動画レクチャー <b-icon icon="rocket" size="is-large" />
    </h2>
    <iframe
      width="100%"
      height="315"
      src="https://www.youtube.com/embed/1Co3RqTzaew"
      frameborder="0"
      allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
      allowfullscreen
    >
    </iframe>
    <div class="content mt-2 p-3 has-background-white">
      <h1>Hello World</h1>
      <p>
        Lorem ipsum<sup><a>[1]</a></sup> dolor sit amet, consectetur adipiscing
        elit. Nulla accumsan, metus ultrices eleifend gravida, nulla nunc varius
        lectus, nec rutrum justo nibh eu lectus. Ut vulputate semper dui. Fusce
        erat odio, sollicitudin vel erat vel, interdum mattis neque. Sub<sub
          >script</sub
        >
        works as well!
      </p>
      <h2>Second level</h2>
      <p>
        Curabitur accumsan turpis pharetra
        <strong>augue tincidunt</strong> blandit. Quisque condimentum maximus
        mi, sit amet commodo arcu rutrum id. Proin pretium urna vel cursus
        venenatis. Suspendisse potenti. Etiam mattis sem rhoncus lacus dapibus
        facilisis. Donec at dignissim dui. Ut et neque nisl.
      </p>

      <h4>Fourth level</h4>
      <p>
        Nulla efficitur eleifend nisi, sit amet bibendum sapien fringilla ac.
        Mauris euismod metus a tellus laoreet, at elementum ex efficitur.
      </p>

      <h6>Sixth level</h6>
      <p>
        Cras in nibh lacinia, venenatis nisi et, auctor urna. Donec pulvinar
        lacus sed diam dignissim, ut eleifend eros accumsan. Phasellus non
        tortor eros. Ut sed rutrum lacus. Etiam purus nunc, scelerisque quis
        enim vitae, malesuada ultrices turpis. Nunc vitae maximus purus, nec
        consectetur dui. Suspendisse euismod, elit vel rutrum commodo, ipsum
        tortor maximus dui, sed varius sapien odio vitae est. Etiam at cursus
        metus.
      </p>
    </div>
    <nuxt-link to="check" class="button">確認チェックへ進む</nuxt-link>
  </section>
</template>

<style scoped>
.panel-block {
  background: white;
}
</style>
