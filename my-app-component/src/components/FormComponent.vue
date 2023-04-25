<template>
  <form @submit.prevent="submitForm">
    <div class="form-control">
      <label for="emp-name">ชื่อพนักงาน</label>
      <input type="text" v-model.trim="employee.name" />
    </div>
    <div class="form-control">
      <label for="emp-salary">เงินเดือน</label>
      <input type="number" v-model="employee.salary" />
    </div>
    <div class="form-control">
      <label for="emp-department">ตำแหน่งงาน</label>
      <select v-model="employee.department">
        <option value="Marketing">Marketing</option>
        <option value="Finance">Finance</option>
        <option value="Sales">Sales</option>
      </select>
    </div>
    <div class="form-control">
      <h2>เพศ</h2>
      <div>
        <input
          type="radio"
          value="ชาย"
          v-model="employee.gender"
          id="gender-name-men"
        />
        <label for="gender-name-men">ชาย</label>
      </div>
      <div>
        <input
          type="radio"
          value="หญิง"
          v-model="employee.gender"
          id="gender-name-women"
        />
        <label for="gender-name-women">หญิง</label>
      </div>
    </div>
    <div class="form-control">
      <h2>ทักษะด้านภาษา</h2>
      <div>
        <input
          type="checkbox"
          value="ภาษาอังกฤษ"
          v-model="employee.skill"
          id="skill-eng"
        />
        <label for="skill-eng">ภาษาอังกฤษ</label>
      </div>
      <div>
        <input
          type="checkbox"
          value="ภาษาไทย"
          v-model="employee.skill"
          id="skill-thai"
        />
        <label for="skill-thai">ภาษาไทย</label>
      </div>
      <div>
        <input
          type="checkbox"
          value="ภาษาจีน"
          v-model="employee.skill"
          id="skill-chinese"
        />
        <label for="skill-chinese">ภาษาจีน</label>
      </div>
    </div>
    <div>
      <button>บันทึกข้อมูล</button>
    </div>
  </form>
</template>

<script>
export default {
  name: "FormComponent",
  data() {
    return {
      employee: {
        name: "",
        salary: 0,
        department: "Marketing",
        gender: "",
        skill: [],
      },
    };
  },
  methods: {
    submitForm() {
      const newEmployee = {
        name: this.employee.name,
        salary: this.employee.salary,
        department: this.employee.department,
        gender: this.employee.gender,
        skill: this.employee.skill,
      };
      this.$emit("save", newEmployee);
      this.resetForm();
    },
    resetForm() {
      this.employee.name = "";
      this.employee.salary = 0;
      this.employee.department = "Marketing";
      this.employee.gender = "";
      this.employee.skill = [];
    },
  },
};
</script>

<style scoped>
form {
  margin: 2rem auto;
  max-width: 40rem;
  border-radius: 12px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.5);
  padding: 2rem;
  background: #fff;
}
.form-control {
  margin: 0.5rem 0;
}
label {
  font-weight: bold;
}
input,
select {
  display: block;
  width: 100%;
  font: inherit;
  margin-top: 0.5rem;
}
button {
  font: inherit;
  background: cadetblue;
  color: white;
  cursor: pointer;
  padding: 0.5rem 1rem;
  border-radius: 10px;
}
input[type="radio"],
input[type="checkbox"] {
  display: inline-block;
  width: auto;
  margin-right: 1rem;
}
input[type="radio"] + label,
input[type="checkbox"] {
  font-weight: normal;
}
h2 {
  font-size: 1rem;
  margin: 0.5rem 0;
}
</style>
