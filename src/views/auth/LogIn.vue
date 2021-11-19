<template>
  <form class="auth" @submit.prevent="getValidation">
    <h1 class="headerH1">Sign In</h1>
    <div class="main">
      <input class="input big" type="email" placeholder="Email" v-model="email" required />
      <input class="big" type="password" placeholder="Password" v-model="password" required maxlength="32" />
      <div class="buttons">
        <button class="button small">Log In</button>
        <router-link class="button small" :to="{name: 'SignUp'}">Sing Up</router-link>
      </div>
    </div>
  </form>
</template>

<script>
import { Firebase } from "@/firebase/firebase.config";

export default {
  name: "LogIn",
  data() {
    return {
      email: null,
      password: null
    };
  },
  methods: {
    getValidation() {
      if (this.email === "niki@gmil.com" && this.password === "123456") {
        alert("Hi");
      }
      Firebase.auth().signInWithEmailAndPassword(this.email.trim(), this.password).then(() => {
        this.$router.push({ name: "Home" });
      }).catch((error) => {
        alert(error.message);
      });
    }
  }
};
</script>

<style lang="less" scoped>
.main {
  margin-top: 100px;
}

.input {
  margin-bottom: 40px;
}

.error {
  color: #EA7C69;
  margin-top: 10px;
  width: 357px;
}

.buttons {
  display: flex;
  justify-content: space-between;
  margin-top: 90px;
}
</style>
