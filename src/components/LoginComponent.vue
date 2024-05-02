<template>
  <div>
    <input v-model="username" placeholder="Username" />
    <input v-model="password" placeholder="Password" type="password" />
    <button @click="login">Login</button>
  </div>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";
import axios from "axios";

// @Options({
//   //在类组件中，数据需要在data()方法中定义
// })
export default class App extends Vue {
  username = "";
  password = "";

  // 在类组件中定义方法，可以直接在类的主体中定义
  async login() {
    try {
      await axios.post(
        "http://localhost:8081/login",
        {
          username: this.username,
          password: this.password,
        },
        { withCredentials: true }
      );
      console.log("Login successful");
    } catch (error) {
      console.error("Login failed", error);
    }
  }

  mounted() {
    document.title = "Login Page";
  }
}
</script>
