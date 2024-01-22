<script setup>

</script>

<template lang="pug">
.kanban-board
  .kanban-board__container
    .kanban-board__container-header Title
    .kanban-board__card.card
      .card__heading Backlog
      .card__image
        img(
          src="/images/item.jpg"
          alt=""
        )
      .card__label In progess
      .card__title Drag me to 'In progress' section
      .card__action
    .kanban-board__card.card
      .card__heading Backlog
      .card__label In progess
      .card__title Drag me to 'In progress' section
      .card__action
    .kanban-board__card.card
      .card__heading Backlog
      .card__label In progess
      .card__title Website Design: New cards for blog section and profile details
      .card__action
  .kanban-board__container
    .kanban-board__container-header Title
    .kanban-board__card.card
      .card__heading Backlog
      .card__label In progess
      .card__title Drag me to 'In progress' section
      .card__action
    .kanban-board__card.card
      .card__heading Backlog
      .card__label In progess
      .card__title Drag me to 'In progress' section
      .card__action
    .kanban-board__card.card
      .card__heading Backlog
      .card__label In progess
      .card__title Website Design: New cards for blog section and profile details
      .card__action

</template>

<style lang="scss">
.kanban-board {
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
    background-color: #42b883;
    color: #fff;
    padding: 0px 7px;
    display: inline-flex;
    justify-content: left;
    border-radius: 6px;
    margin-bottom: 10px;
    font-size: 12px;
  }
}

</style>