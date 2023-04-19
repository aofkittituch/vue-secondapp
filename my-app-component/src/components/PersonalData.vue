<template>
  <div>
    <h1>
      {{ message }}
    </h1>
  </div>
</template>

<script>
export default {
  name: "PersonalData",
  data() {
    return {
      message: "ข้อมูลพนักงานแต่ละคน",
    };
  },
};
</script>

<style scoped>
h1 {
  color: red;
}
</style>
