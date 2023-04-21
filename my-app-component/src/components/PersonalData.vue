<template>
  <CardEmployee>
    <template v-slot:card-header>
      <h1>ชื่อ : {{ name }}</h1>
    </template>
    <template v-slot:card-button>
      <button @click="showDescription(id)">ดูรายละเอียด</button> &nbsp;
      <button @click="deleteEmployee(id)">ลบข้อมูล</button>
    </template>
    <template v-slot:card-content>
      <transition name="fade">
        <div v-show="isVisible">
          <p>เงินเดือน : {{ salary }} ตำแหน่ง : {{ department }}</p>
        </div>
      </transition>
    </template>
  </CardEmployee>
</template>

<script>
import CardEmployee from "./CardEmployee.vue";
export default {
  name: "PersonalData",
  components: {
    CardEmployee,
  },
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
button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #ff0077;
  background: #ff0077;
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}
.fade-enter-from {
  opacity: 0;
}
.fade-enter-active {
  transition: all 0.5s linear;
}
</style>
