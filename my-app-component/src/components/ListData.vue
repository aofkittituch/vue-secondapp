<template>
  <div>
    <ul>
      <PersonalData
        v-for="(item, index) in employee"
        :key="index"
        :name="item.name"
        :salary="item.salary"
        :department="item.department"
        :gender="item.gender"
        :skill="item.skill"
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
  props: ["employee"],
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
