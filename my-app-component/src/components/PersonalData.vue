<template>
  <li>
    <h1>ชื่อ : {{ name }}</h1>
    <button @click="showDescription(id)">ดูรายละเอียด</button> &nbsp;
    <button @click="deleteEmployee(id)">ลบข้อมูล</button>
    <div v-show="isVisible">
      <p>เงินเดือน : {{ salary }} ตำแหน่ง : {{ department }}</p>
    </div>
  </li>
</template>

<script>
export default {
  name: "PersonalData",
  props: {
    id: { type: Number },
    name: { type: String, required: true },
    salary: { type: Number, required: true, default: 15000 },
    department: { type: String, required: true },
    isVisible: { type: Boolean },
  },
  methods: {
    showDescription(id) {
      this.$emit("show", id);
    },
    deleteEmployee(id) {
      this.$emit("delete", id);
    },
  },
};
</script>

<style scoped>
li {
  margin: 1rem 0;
  font-size: 1.2rem;
  font-weight: bold;
  background: #8ddbac;
  padding: 0.5rem;
  color: #1f1f1f;
  border-radius: 25px;
}
button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #ff0077;
  background: #ff0077;
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}
</style>
