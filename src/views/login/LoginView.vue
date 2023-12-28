<template>
    <div id='login'>
        <p>登入页面</p>
        <el-form :model="ruleForm" :rules="rules" ref="ruleForm" label-width="100px" class="demo-ruleForm">
            <!-- username -->
            <el-form-item label="用户名" prop="name">
                <el-input v-model="ruleForm.name"></el-input>
            </el-form-item>

            <!-- password -->
            <el-form-item label="密码" prop="passworld">
                <el-input type='passworld' v-model="ruleForm.name"></el-input>
            </el-form-item>

            <el-form-item>
                <el-button type="primary" @click="submitForm('ruleForm')">登入</el-button>
            </el-form-item>
        </el-form>
    </div>
</template>

<script>
export default {
    data() {
        return {
            ruleForm: {
                name: '',
                passworld: ''
            }
        }
    },
    rules: {
        name: [
            { required: true, message: '请输入姓名', trigger: 'blur' },
            { min: 3, max: 5, message: '长度在3到5个字符', trigger: 'blur' }
        ],
        passworld: [
            { required: true, message: '请输入密码', trigger: 'blur' },
            { min: 3, max: 5, message: '长度在8到16个字符', trigger: 'blur' }
        ]
    },
    methods: {
        submitForm(){
            this.$router.push('/home')
        }
    }

}
</script>