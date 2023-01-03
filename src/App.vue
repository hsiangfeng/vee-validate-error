<script setup>
import { ref } from 'vue';

const user = ref({
  account: '',
  password: '',
});
</script>

<template>
  <VForm
  v-slot="{ errors }"
  @submit="login"
  >
    <div>
      <label for="account">帳號</label>
      <VField
        id="account"
        v-model.trim="user.account"
        name="帳號"
        type="email"
        :class="{ 'is-invalid': errors['帳號'] }"
        rules="required|email"
      />
      <ErrorMessage
        name="帳號"
      />
    </div>
    <div>
      <label for="password">密碼</label>
      <VField
        id="password"
        v-model.trim="user.password"
        name="密碼"
        type="password"
        :class="{ 'is-invalid': errors['密碼'] }"
        rules="required"
      />
      <ErrorMessage
        name="密碼"
      />
    </div>
  </VForm>
</template>

<style scoped>
</style>
