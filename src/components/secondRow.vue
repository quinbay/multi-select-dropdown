<template>
  <tr>
    <td></td>
    <td>{{ idx + 1 }}</td>
    <td>{{ skill.name }}</td>
    <td>{{ skill.level }}</td>
  </tr>
</template>
<script>
export default {
  name: "secondRow",
  props: {
    skill: Object,
    idx: Number,
  },
};
</script>
