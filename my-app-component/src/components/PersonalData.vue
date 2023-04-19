<template>
  <div>
    <h1>ชื่อ : {{ name }} เงินเดือน : {{ salary }}</h1>
  </div>
</template>

<script>
export default {
  name: "PersonalData",
  props: {
    name: { type: String, required: true },
    salary: { type: Number, required: true, default: 15000 },
  },
};
</script>

<style scoped>
h1 {
  color: red;
}
</style>
