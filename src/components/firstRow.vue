<template>
  <tr>
    <td>{{ idx + 1 }}</td>
    <td>{{ data.name }}</td>
    <td>{{ data.role }}</td>
    <td><button v-on:click="toggle">show</button></td>
  </tr>
</template>
<script>
export default {
  name: "firstRow",
  props: {
    data: Object,
    idx: Number,
    parent: Object,
  },
  methods: {
    toggle() {
      this.$emit("changeIdx", this.idx);
    },
  },
};
</script>
