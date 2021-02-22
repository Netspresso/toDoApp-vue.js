<template>
  <div>
    <div class="item">
      <p>Nowe todo: {{ newItem }}</p>
      <input type="text" placeholder="todo" v-model="newItem" />
      <button @click="addItem">Dodaj</button>
    </div>
    <toDoItem
      v-for="item in items"
      v-bind:key="item.id"
      v-bind:item="item"
      @onItemDone="doItem"
    />
  </div>
</template>

<script>
import toDoItem from "./toDoItem.vue";

export default {
  components: {
    toDoItem,
  },
  data() {
    return {
      newItem: "",
      items: [
        { title: "Zrobic zakupy", completed: false, id: 1 },
        { title: "Zrobic pranie", completed: true, id: 2 },
      ],
    };
  },
  methods: {
    addItem() {
      this.items.push({
        title: this.newItem,
        completed: false,
        id: Math.random(),
      });
      this.newItem = "";
    },
    doItem(id) {
      const index = this.items.findIndex((e) => e.id === id);
      this.items[index].completed = true;
    },
  },
};
</script>

<style>
.item {
  border: 1px solid#cdcdcd;
  margin: 8px;
  padding: 10px;
}

.completed {
  opacity: 0.5;
}

.completed h2 {
  text-decoration: line-through;
}
</style>
