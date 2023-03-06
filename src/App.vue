<script setup>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'

import { reactive, ref, computed, watch } from "vue";

const student = reactive({ firstname: "", lastname: "", birthyear: 1900 });
const age = ref(0);

const calculatedAge = () => {
  age.value = (new Date().getFullYear()) - student.birthyear;
};

const fullname = computed(() => "" + student.firstname + " " + student.lastname)

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
          <input type="number" v-model="student.birthyear" placeholder="Birth Year" min="1900" /><br />
          FullName: {{ fullname }}<br />
          Age: {{ age }}
      </div>
      <Footer />
    </div>
</template>
