<script setup>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import {reactive, ref, watch } from 'vue'

import { reactive, ref, watch } from "vue";

const student = reactive({ firstname: "", lastname: "", birthyear });
const age = ref(0);

const calculatedAge = () => {
  age.value = (new Date().getFullYear()) - student.birthyear;
};



watch(student, (val, oldval) => {
  console.log(val, oldval);
  calculatedAge();
});
</script>

<template>
    <div class="wrapper">
      <Header text="Vue Script Setup App" />
      <div>
          <h2>Student Enrollment</h2>
          <input type="text" v-model="student.firstname" placeholder="Student First Name" />
          <input type="text" v-model="student.lastname" placeholder="Student Last Name" />
          <input type="number" v-model="student.birthyear" placeholder="Birth Year" />
          <label {{ age }} />
      </div>
      <Footer />
    </div>
</template>
