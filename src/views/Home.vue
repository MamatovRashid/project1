<template>
  <div class="home w-full min-h-screen flex justify-center items-center">
    <div class="relative p-5 w-80 font-serif">
      <h1 class="text-white text-2xl mb-5">Login</h1>
      <div class="bg-white rounded opacity-10 w-full h-full absolute top-0 left-0"></div>
      <el-form :model="form" :rules="rules" ref="form" class="demo-ruleForm">
        <el-form-item prop="login">
          <el-input size="medium" v-model="form.login" placeholder="Login" clearable></el-input>
        </el-form-item>
        <el-form-item prop="password">
          <el-input size="medium" v-model="form.password" placeholder="Parol" show-password></el-input>
        </el-form-item>
        <el-form-item class="pt-4 buttons">
          <button @click.prevent="submitForm('form')" class="submit border px-4 py-1.5 rounded text-base font-semibold text-white hover:bg-blue-500 hover:border-blue-500 mx-2">Kirish</button>
          <button @click.prevent="resetForm('form')" class="clear border px-4 py-1.5 rounded text-base font-semibold text-white hover:bg-gray-800 hover:border-gray-800 mx-2">Tozalash</button>
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  components: {},
  data() {
    return {
      form: {
        login: "",
        password: ""
      },
      rules: {
        login: [
          { required: true, message: 'Login', trigger: 'blur' }
        ],
        password: [
          { required: true, message: 'Parol', trigger: 'blur' }
        ]
      }
    }
  },
  methods: {
    submitForm(formName) {
      this.$refs[formName].validate((valid) => {
        if (valid) {
          this.$notify({
            title: 'Muaffaqiyatli',
            message: 'Tizimga hush kelibsiz!',
            type: 'success'
          });
        } else {
          return false;
        }
      });
    },
    resetForm(formName) {
      this.$refs[formName].resetFields();
    }
  },
};
</script>

<style>
.home {
  background-image: url("https://user-images.githubusercontent.com/26748614/96337246-f14d4580-1085-11eb-8793-a86d929e034d.jpg");
}
.home .el-input__inner{
  background: transparent;
  color: #fff;
}
.home .submit:hover{
  box-shadow: 0 0 100px 2px rgb(59, 130, 246);
}
.home .clear:hover{
  box-shadow: 0 0 10px 2px rgb(31, 41, 55);
}
.home .buttons{
  margin-bottom: 10px;
}
</style>
