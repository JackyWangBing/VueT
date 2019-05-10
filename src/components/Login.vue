<template>
  <Form ref="login" :model="loginInfo" :rules="rulesLogin">
    <FormItem label="用户名" prop="userName">
      <Input v-model="loginInfo.userName" placeholder="用户名"></Input>
    </FormItem>
    <FormItem label="密码" prop="password">
      <Input v-model="loginInfo.password" placeholder="密码" type="password"></Input>
    </FormItem>
    <FormItem>
      <Button type="primary">登录</Button>
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
        password: [
          { required: true, message: "请输入密码.", trigger: "blur" }
        ]
      }
    };
  }
};
</script>

<style lang="" scoped>
</style>