<template>
  <div class="item" v-bind:class="{ completed: item.completed }">
    <h2>{{ item.title }}</h2>
    <button v-if="!item.completed" @click="doItem">Zakończ</button>
  </div>
</template>

<script>
export default {
  props: ["item"],
  methods: {
    doItem() {
      this.$emit("onItemDone", this.item.id);
    },
  },
};
</script>