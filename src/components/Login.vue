<template>
  <Form ref="login" :model="loginInfo" :rules="rulesLogin" :label-width="80">
    <FormItem label="用户名" prop="userName">
      <Input v-model="loginInfo.userName" placeholder="用户名" clearable></Input>
    </FormItem>
    <FormItem label="密码" prop="password">
      <Input v-model="loginInfo.password" placeholder="密码" type="password" clearable></Input>
    </FormItem>
    <FormItem>
      <Button type="primary" @click="toLogin">登录</Button>
    </FormItem>
  </Form>
</template>

<script>
export default {
  name: "Login",
  data() {
    return {
      loginInfo: {
        userName: "test1",
        password: "test1"
      },
      rulesLogin: {
        userName: [
          { required: true, message: "请输入用户名", trigger: "blur" }
        ],
        password: [{ required: true, message: "请输入密码.", trigger: "blur" }]
      }
    };
  },
  methods: {
    toLogin() {
      this.$refs["loginInfo"].validate(valid => {
        if (valid) {
          this.$Message.success("Success!");
        } else {
          this.$Message.error("Fail!");
        }
      });
    }
  }
};
</script>

<style lang="" scoped>
</style>