<script setup>

</script>

<template lang="pug">
header.header
  .header__logo Kanban board
.kanban-board
  .kanban-board__container
    .kanban-board__container-header Title
    .kanban-board__card.card
      .card__image
        img(
          src="/images/item.jpg"
          alt=""
        )
      .card__label.primary In Backlog
      .card__title Drag me to 'In progress' section
      .card__action
    .kanban-board__card.card
      .card__label.primary In progress
      .card__title Drag me to 'In progress' section
      .card__action
    .kanban-board__card.card
      .card__label.warning In progress
      .card__title Website Design: New cards for blog section and profile details
      .card__action
    .kanban-board__container-action + Add card
  .kanban-board__container
    .kanban-board__container-header Title
    .kanban-board__card.card
      .card__label.secondary In progress
      .card__title Drag me to 'In progress' section
      .card__action
    .kanban-board__card.card
      .card__label.success In progress
      .card__title Drag me to 'In progress' section
      .card__action
    .kanban-board__card.card
      .card__label.danger Bug
      .card__title Website Design: New cards for blog section and profile details
      .card__action
    .kanban-board__container-action + Add card

</template>

<style lang="scss">
.header {
  background-color: #1a1a1a;
  margin-bottom: 20px;
  padding: 20px;
}
.kanban-board {
  padding: 0 20px;
  display: flex;
  align-items: flex-start;
  &__container {
    width: 300px;
    margin-right: 12px;
    background-color: #1a1a1a;
    border-radius: 8px;
    padding: 10px;
    &-header {
      margin-bottom: 10px;
    }
  }
}
.card {
  background-color: #242424;
  padding: 15px;
  border-radius: 6px;
  margin-bottom: 10px;
  border: 1px solid #242424;
  &:hover {
    border: 1px solid #616161;
  }
  &__heading {
    margin-bottom: 10px;
  }
  &__image {
    margin-bottom: 10px;
    img {
      max-width: 100%;
      border-radius: 6px;
    }
  }
  &__label {
    color: #fff;
    padding: 0px 7px;
    display: inline-flex;
    justify-content: left;
    border-radius: 4px;
    margin-bottom: 10px;
    font-size: 12px;
  }
}

</style>