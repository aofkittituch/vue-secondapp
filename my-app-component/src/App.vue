<template>
  <div>
    <FormComponent />
    <ListData />
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
};
</script>
