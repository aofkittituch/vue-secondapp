<template>
  <div>
    <PersonalData name="kong" salary=10000 />
    <PersonalData name="jojo" salary=15000 />
    <PersonalData name="aof" salary=15000 />
  </div>
</template>

<script>
import PersonalData from "./PersonalData.vue";
export default {
  name: "ListData",
  components: {
    PersonalData,
  },
};
</script>

<style></style>

<!-- note -->
<!-- parent component -> child component use props -->
<!-- child component -> parent component use event -->
