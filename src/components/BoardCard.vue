<script setup>
const props = defineProps({
  content: Object
})
</script>

<template lang="pug">
.card
    .card__image(
      v-if="content.image"
    )
      img(
        :src="`/images/${content.image}`"
      )
    .card__label.primary {{ content.label }}
    .card__title {{ content.title }}
</template>

<style lang="scss" scoped>

</style>