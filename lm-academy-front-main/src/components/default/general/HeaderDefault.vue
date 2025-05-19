<template>
  <header>
    <div class="flex justify-between items-center border-b-textPrimary border-b-4 py-4">
      <div class="logo text-5xl text-textPrimary">LM Academy</div>
      <nav class="text-3xl flex gap-2">
        <router-link :to="{ name: 'home' }" active-class="router-link-active">Home</router-link>
        <router-link :to="{ name: 'AboutUs' }" active-class="router-link-active">About Us</router-link>
        <router-link to="/login" active-class="router-link-active">Login</router-link>
      </nav>
    </div>
  </header>
</template>
