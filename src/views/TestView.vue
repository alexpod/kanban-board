<template>
  <div class="row">
    <div class="col-3">
      <h3>Draggable 1</h3>
      <draggable
        class="list-group"
        :list="list1"
        group="people"
        itemKey="name"
      >
        <template #item="{ element, index }">
          <div class="list-group-item">{{ element.name }} {{ index }}</div>
        </template>
      </draggable>
    </div>

    <div class="col-3">
      <h3>Draggable 2</h3>
      <draggable
        class="list-group"
        :list="list2"
        group="people"
        itemKey="name"
      >
        <template #item="{ element, index }">
          <div class="list-group-item">{{ element.name }} {{ index }}</div>
        </template>
      </draggable>
    </div>
  </div>
</template>
<script>
import draggable from 'vuedraggable'

export default {
  name: "two-lists",
  display: "Two Lists",
  order: 1,
  components: {
    draggable
  },
  data() {
    return {
      list1: [
      {
        id: 1,
        image: 'item.jpg',
        label: 'Hold',
        name:'Drag me to "In progress" section',
        description: ''
      },
      {
        id: 2,
        image: '',
        label: 'In Backlog',
        name:'Add a new feature',
        description: ''
      },
      {
        id: 3,
        image: '',
        label: 'Hold',
        name:'Website Design: New cards for blog section and profile details',
        description: ''
      },
      {
        id: 4,
        image: '',
        label: '',
        name:'Add a new feature',
        description: ''
      },
      ],
      list2: [
        { name: "5 Juan", id: 5 },
        { name: "6 Edgard", id: 6 },
        { name: "7 Johnson", id: 7 }
      ]
    };
  },
  methods: {
    /* add: function() {
      this.list.push({ name: "Juan" });
    },
    replace: function() {
      this.list = [{ name: "Edgard" }];
    },
    clone: function(el) {
      return {
        name: el.name + " cloned"
      };
    },
    log: function(evt) {
      window.console.log(evt);
    } */
  }
};
</script>

<style lang="scss">
.list-group-item {
  cursor: move;
  position: relative;
  display: block;
  padding: 0.75rem 1.25rem;
  background-color: #fff;
  border: 1px solid rgba(0,0,0,.125);
  font-size: 1rem;
    font-weight: 400;
    line-height: 1.5;
    color: #212529;
}
</style>