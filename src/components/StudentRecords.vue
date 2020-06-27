<template>
  <div>
    <el-row style="border: 1px solid lightgray;">
      <el-col>
        <el-table
          :data="studentsData"
          :default-sort="{prop: 'age', order: 'ascending'}"
          @selection-change="handleSelectionChange"
          height="400"
        >
          <el-table-column type="selection"></el-table-column>
          <el-table-column prop="name" label="Name"></el-table-column>
          <el-table-column sortable prop="age" label="Age" width="80"></el-table-column>
          <el-table-column label="Address Details">
            <el-table-column prop="state" label="State"></el-table-column>
            <el-table-column prop="city" label="City"></el-table-column>
            <el-table-column prop="address" label="Address"></el-table-column>
            <el-table-column prop="zip" label="Zip"></el-table-column>
          </el-table-column>
          <el-table-column prop="tag" label="Tag" width="120">
            <template slot-scope="scope">
              <el-tag
                :type="scope.row.tag === 'Employed' ? 'success' : 'primary'"
                disable-transitions
              >{{scope.row.tag}}</el-tag>
            </template>
          </el-table-column>
        </el-table>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import { STUDENTS_DATA } from "../data/students_data.js";

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
      this.selectedStudents = val;
    }
  }
};
</script>
