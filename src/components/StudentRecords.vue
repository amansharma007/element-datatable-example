<template>
  <div>
    <el-row style="border: 1px solid lightgray;">
      <el-col>
        <el-table :data="studentsData" @selection-change="handleSelectionChange" height="400">
          <el-table-column type="selection"></el-table-column>
          <el-table-column prop="name" label="Name"></el-table-column>
          <el-table-column label="Address Details">
            <el-table-column prop="state" label="State"></el-table-column>
            <el-table-column prop="city" label="City"></el-table-column>
            <el-table-column prop="address" label="Address"></el-table-column>
            <el-table-column prop="zip" label="Zip"></el-table-column>
          </el-table-column>
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
      studentsData: STUDENTS_DATA,
      selectedStudents: []
    };
  },
  methods: {
    handleSelectionChange(val) {
      this.selectedStudents = val
    }
  }
};
</script>
