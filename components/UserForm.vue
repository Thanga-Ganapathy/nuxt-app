<template>
    <el-form ref="form" :model="form" label-width="120px">
        <el-form-item label="Name">
            <el-input v-model="form.name"></el-input>
        </el-form-item>
        <el-form-item label="Location">
            <el-select v-model="form.location" placeholder="Select">
                <el-option label="Bangalore" value="Bangalore"></el-option>
                <el-option label="Chennai" value="Chennai"></el-option>
                <el-option label="Delhi" value="Delhi"></el-option>
            </el-select>
        </el-form-item>
        <el-form-item label="Active">
            <el-switch v-model="form.active"></el-switch>
        </el-form-item>
        <el-form-item label="Gender">
            <el-radio-group v-model="form.gender">
                <el-radio label="Male"></el-radio>
                <el-radio label="Female"></el-radio>
                <el-radio label="Trans"></el-radio>
            </el-radio-group>
        </el-form-item>
        <el-form-item>
            <el-button type="primary" @click="onSubmit">Create</el-button>
        </el-form-item>
    </el-form>

</template>

<script>
export default {
    data() {
        return {
            form: {
                name: '',
                location: '',
                active: false,
                gender: '',
            }
        }
    },
    methods: {
        onSubmit() {
            this.$store.commit('addUser', this.form)
            this.form = {}
        }
    }
}
</script>