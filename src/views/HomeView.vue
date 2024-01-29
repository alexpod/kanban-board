<script setup>
import BoardCard from "@/components/BoardCard.vue";
import draggable from 'vuedraggable'
import { ref } from "vue";

draggable

const drag = ref(false)
const columns = ref({})
const cards = ref({})
const board = ref([
  {
    id: 1,
    title: 'Todo',
    cards: [
      {
        id: 1,
        image: 'item.jpg',
        labels: [
          {
            id: 1,
            name: 'Hold',
            class: 'primary'
          },
        ],
        title:'Drag me to "In progress" section',
        description: ''
      },
      {
        id: 2,
        image: '',
        labels: [
          {
            id: 1,
            name: 'In Backlog',
            class: 'secondary'
          },
        ],
        title:'Add a new feature',
        description: ''
      },
      {
        id: 3,
        image: '',
        labels: [
          {
            id: 1,
            name: 'Hold',
            class: 'primary'
          },
        ],
        title:'Website Design: New cards for blog section and profile details',
        description: ''
      },
      {
        id: 4,
        image: '',
        labels: [
          {
            id: 1,
            name: 'In progress',
            class: 'success'
          },
        ],
        title:'Add a new feature',
        description: ''
      },
    ]
    
  },
  {
    id: 2,
    title: 'In progress',
    cards: [
      {
        id: 1,
        image: '',
        labels: [
          {
            id: 1,
            name: 'In progress',
            class: 'success'
          },
        ],
        title:'Title 1',
        description: ''
      },
      {
        id: 2,
        image: '',
        labels: [
          {
            id: 1,
            name: 'Bug',
            class: 'danger'
          },
        ],
        title:'Title 2',
        description: ''
      },
    ]
  },
])

</script>
<template lang="pug">
header.header
  .header__logo Kanban board
.kanban-board
  .kanban-board__container(
    v-for="column in board"
    :id="column.id"
  )
    .kanban-board__container-header {{ column.title }}
    .kanban-board__card-wrapper
      draggable(
        :list="column.cards"
        itemKey="title"
        group="people"
      )
        template(
          #item="{ element, index }"
        )
          .kanban-board__card.card
            .card__image(
              v-if="element.image"
            )
              img(
                :src="`/images/${element.image}`"
                alt=""
              )
            .card__label(
              v-if="element.labels"
              v-for="label in element.labels"
              :class="label.class"
            ) {{ label.name }}
            .card__title {{ element.title }}


    .kanban-board__container-action + Add card
  // .kanban-board__container
    .kanban-board__container-header In progress
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