<template>
  <div
    @click="cardClicked()"
    :class="{ panel: true, active: isActive }"
    :style="{ backgroundImage: `url(${imageURL})` }"
  >
    <h3>{{ title }}</h3>
  </div>
</template>

<script>
export default {
  name: 'EventCard',
  props: ['title', 'imageURL', 'isActive', 'cardNumber'],
  methods: {
    cardClicked() {
      this.$emit('clicked', this.cardNumber);
    },
  },
};
</script>

<style></style>
