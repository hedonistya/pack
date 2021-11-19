<template>
  <form class="auth" @submit.prevent="pressed" method="post">
    <h1 class="headerH1">Sign Up</h1>
    <div class="main">
      <div class="main__name">
        <input class="small" type="text" placeholder="Name" required v-model="name" />
        <input class="small" type="text" placeholder="Surname" v-model="surname" required />
      </div>
      <input class="input big" type="email" placeholder="Email" v-model="email" required />
      <input class="big" type="password" placeholder="Password" v-model="password" required />
      <div class="buttons">
        <button class="button small">Sign Up</button>
      </div>
    </div>
  </form>
</template>

<script>
export default {
  name: "SignUp"
};
</script>

<style lang="less" scoped>
.main {
  margin-top: 70px;
}

.main__name {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin-bottom: 26px;
}

.input {
  margin-bottom: 26px;
}

.buttons {
  display: flex;
  justify-content: center;
  margin-top: 60px;
}
</style>
