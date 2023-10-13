<template>
  <div>
    <select v-model="selected">
      <option disabled value="">Please select one</option>
      <option>A</option>
      <option>B</option>
      <option>C</option>
    </select>
  </div>
</template>

<script>
import axios from "axios";
/* import Swal from "sweetalert2"; */

export default {
  data() {
    return {
      username: "",
      password: "",
      error: null,
    };
  },
  mounted() {
    console.log("mounted() called.......");
  },
  methods: {
    async fetchContries() {
      try {
        const response = await axios.get(
          "http://localhost:8080/api/v1/country"
        );
        console.log(response.data);

        //obtener todos los paises
        this.countries = response.data;
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>

<style scoped></style>
