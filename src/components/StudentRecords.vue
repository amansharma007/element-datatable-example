<template>
  <div>
    <el-row style="border: 1px solid lightgray;">
      <el-col>
        <el-table :data="studentsData" height="400">
          <el-table-column prop="name" label="Name"></el-table-column>

        </el-table>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import { STUDENTS_DATA } from '../data/students_data.js'

export default {
  name: "StudentRecords",
  data() {
    return {
      studentsData: STUDENTS_DATA
    };
  }
};
</script>
