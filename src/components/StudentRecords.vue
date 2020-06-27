<template>
  <div>
    <el-row>
      <el-col>
        <el-table :data="studentsData">
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
        }
      ]
    };
  }
};
</script>
