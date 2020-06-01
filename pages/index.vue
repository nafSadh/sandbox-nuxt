<template>
  <section class="section">
    <div class="columns is-mobile">
      <card title="Some card" icon="arrange-bring-to-front">
        Some text on a card.
      </card>
    </div>
  </section>
</template>

<script>
import Card from '~/components/Card'

export default {
  name: 'HomePage',

  components: {
    Card
  }
}
</script>
