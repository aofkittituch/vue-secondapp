<template>
  <div>
    <ul>
      <PersonalData
        v-for="item in employees"
        :key="item.id"
        :name="item.name"
        :salary="item.salary"
        :department="item.department"
        :isVisible="item.isVisible"
        :id="item.id"
        @show="toggleVisible"
      />
    </ul>
  </div>
</template>

<script>
import PersonalData from "./PersonalData.vue";
export default {
  name: "ListData",
  components: {
    PersonalData,
  },
  data() {
    return {
      employees: [
        {
          id: 1,
          name: "kong",
          salary: 40000,
          department: "programmer",
          isVisible: false,
        },
        {
          id: 2,
          name: "aof",
          salary: 30000,
          department: "marketing",
          isVisible: false,
        },
        {
          id: 3,
          name: "jeff",
          salary: 20000,
          department: "sale",
          isVisible: false,
        },
        {
          id: 4,
          name: "bas",
          department: "programmer",
          isVisible: false,
        },
      ],
    };
  },
  methods: {
    toggleVisible(id) {
      this.employees = this.employees.map((item) => {
        if (item.id === id) {
          return { ...item, isVisible: !item.isVisible };
        }
        return item;
      });
    },
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
</style>

<!-- note -->
<!-- parent component -> child component use props -->
<!-- child component -> parent component use custom event -->
