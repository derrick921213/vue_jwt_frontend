<template>
  <div class="login">
    <LoginComponent />
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import LoginComponent from "@/components/LoginComponent.vue"; // @ is an alias to /src

@Options({
  components: {
    LoginComponent,
  },
})
export default class LoginView extends Vue {}
</script>
