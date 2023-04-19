<template>
  <div>
    <ul>
      <PersonalData
        v-for="(item, index) in employees"
        :key="index"
        :name="item.name"
        :salary="item.salary"
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
  props: ["employees"],
};
</script>

<style></style>

<!-- note -->
<!-- parent component -> child component use props -->
<!-- child component -> parent component use event -->
