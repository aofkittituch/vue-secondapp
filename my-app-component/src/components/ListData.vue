<template>
  <div>
    <h1>{{ message }}</h1>
    <PersonalData />
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
      message: "แสดงรายชื่อข้อมูลพนักงานทุกคน",
    };
  },
};
</script>

<style></style>
