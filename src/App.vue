<script setup>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import {reactive, ref, watch } from 'vue'

</script>

<template>
    <div class="wrapper">
      <Header text="Vue Script Setup App" />
      <div>
          <h2>Student Enrollment</h2>
          <input type="text" v-model="student.firstname" placeholder="Student First Name" />
          <input type="text" v-model="student.lastname" placeholder="Student Last Name" />
          <input type="number" v-model="student.age" placeholder="Student Age" />
      </div>
      <Footer />
    </div>
</template>
