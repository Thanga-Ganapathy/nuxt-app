<template>
    <el-table :data="tableData" style="width: 100%">
        <el-table-column type="index" width="50">
        </el-table-column>
        <el-table-column prop="name" label="Name" width="180">
        </el-table-column>
        <el-table-column prop="gender" label="Gender" width="180">
        </el-table-column>
        <el-table-column prop="location" label="Location" width="180">
        </el-table-column>
        <el-table-column prop="active" label="Status" width="180">
            <template slot-scope="scope">
                {{ scope.row.active ? 'Active' : 'Deactivated' }}
            </template>
        </el-table-column>
    </el-table>
</template>

  <script>
  export default {
      data() {
          return {
              tableData: this.$store.getters.getUsers
          }
      }
  }
  </script>