<template>
  <div>
    <FormComponent />
    <ListData :employees="employees" />
  </div>
</template>

<script>
import FormComponent from "./components/FormComponent.vue";
import ListData from "./components/ListData.vue";
export default {
  name: "App",
  components: {
    ListData,
    FormComponent,
  },
  data() {
    return {
      employees: [
        {
          name: "kong",
          salary: 40000,
        },
        {
          name: "aof",
          salary: 30000,
        },
        {
          name: "jeff",
          salary: 20000,
        },
        {
          name: "bas",
          salary: 40000,
        },
        {
          name: "net",
          salary: 10000,
        },
      ],
    };
  },
};
</script>
