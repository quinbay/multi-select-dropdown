<template>
  <table>
    <thead>
      <th>S-No</th>
      <th>Name</th>
      <th>Role</th>
      <th>Action</th>
    </thead>
    <tbody>
      <template v-for="(data, i) in datas">
        <firstRow
          :data="data"
          :idx="i"
          :key="i + 'j'"
          @changeIdx="callback"
        ></firstRow>
        <template v-for="(skill, j) in data.skills">
          <secondRow
            :skill="skill"
            :idx="j"
            :key="j + 'k'"
            v-if="i == selectedIdx"
          ></secondRow>
        </template>
      </template>
    </tbody>
  </table>
</template>
<script>
import firstRow from "@/components/firstRow.vue";
import secondRow from "@/components/secondRow.vue";
export default {
  name: "tableCp",
  props: {},
  components: {
    firstRow,
    secondRow,
  },
  data() {
    return {
      selectedIdx: -1,
      datas: [
        {
          name: "Nishanth",
          role: "Dev",
          skills: [
            {
              name: "Java",
              level: "Expert",
            },
            {
              name: "Python",
              level: "Intermediate",
            },
          ],
        },
        {
          name: "shiyam",
          role: "Dev",
          skills: [
            {
              name: "Java",
              level: "Expert",
            },
            {
              name: "Python",
              level: "Intermediate",
            },
          ],
        },
      ],
    };
  },
  methods: {
    callback(event) {
      if (this.selectedIdx == event) {
        this.selectedIdx = -1;
      } else {
        this.selectedIdx = event;
      }
    },
  },
};
</script>
<style>
table {
  border-collapse: collapse;
  width: 100%;
}
th {
  padding: 1rem;
}
td {
  padding: 0.5rem 1rem;
}
tr:nth-child(even) {
  background-color: #f2f2f2;
}
</style>
