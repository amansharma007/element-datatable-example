<template>
  <div>
    <el-row style="border: 1px solid lightgray;">
      <el-col>
        <el-table
          :data="getSearchedStudents"
          :default-sort="{prop: 'age', order: 'ascending'}"
          @selection-change="handleSelectionChange"
          height="400"
        >
          <el-table-column type="expand">
            <template slot-scope="props">
              <el-row>
                <el-col :span="4">
                  <img :src="props.row.img" />
                </el-col>
                <el-col :span="18">
                  <p>Name: {{ props.row.name }}</p>
                  <p>State: {{ props.row.state }}</p>
                  <p>Birthday: {{ props.row.birthday }}</p>
                  <p>Employment Status: {{ props.row.tag }}</p>
                </el-col>
              </el-row>
            </template>
          </el-table-column>
          <el-table-column type="selection"></el-table-column>
          <el-table-column prop="name" label="Name"></el-table-column>
          <el-table-column sortable prop="age" label="Age" width="80"></el-table-column>
          <el-table-column label="Address Details">
            <el-table-column prop="state" label="State"></el-table-column>
            <el-table-column prop="city" label="City"></el-table-column>
            <el-table-column prop="address" label="Address"></el-table-column>
            <el-table-column prop="zip" label="Zip"></el-table-column>
          </el-table-column>
          <el-table-column
            prop="tag"
            label="Tag"
            width="120"
            :filters="[{ text: 'Employed', value: 'Employed' }, { text: 'Unemployed', value: 'Unemployed' }]"
            :filter-method="filterTag"
          >
            <template slot-scope="scope">
              <el-tag
                :type="scope.row.tag === 'Employed' ? 'success' : 'primary'"
                disable-transitions
              >{{scope.row.tag}}</el-tag>
            </template>
          </el-table-column>
          <el-table-column width="180" align="center">
            <template slot="header">
              <el-input v-model="search" size="mini" placeholder="Type to search" />
            </template>
            <template slot-scope="scope">
              <el-button size="mini" type="danger" @click="handleDelete(scope.$index)">Delete</el-button>
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
      selectedStudents: [],
      search: ""
    };
  },
  computed: {
    getSearchedStudents() {
      let search = this.search;
      return this.studentsData.filter(data =>
        search ? data.name.toLowerCase().includes(search.toLowerCase()) : true
      );
    }
  },
  methods: {
    handleSelectionChange(val) {
      this.selectedStudents = val;
    },
    handleDelete(index) {
      this.studentsData.splice(index, 1);
    },
    filterTag(value, row) {
      return row.tag === value;
    }
  }
};
</script>
