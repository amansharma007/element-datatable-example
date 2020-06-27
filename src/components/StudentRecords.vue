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
export default {
  name: "StudentRecords",
  data() {
    return {
      studentsData: [
        {
          name: "John"
        },
        {
          name: "Janet"
        },
        {
          name: "Rami"
        },
        {
          name: "Sylvestor"
        },
        {
          name: "Gweneth"
        },
        {
          name: "Rakesh"
        },
        {
          name: "Amitabh"
        },
        {
          name: "Rosy"
        },
        {
          name: "Rhea"
        },
        {
          name: "Sailesh"
        },
        {
          name: "Rohit"
        },
        {
          name: "Alan"
        }
      ]
    };
  }
};
</script>
