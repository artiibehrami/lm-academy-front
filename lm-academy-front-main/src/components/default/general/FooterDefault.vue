<script setup>
// No script needed for static footer
</script>

<template>
  <footer class="flex flex-col sm:flex-row justify-between items-center border-t-textPrimary border-t-4 py-4 px-4 mt-8">
    <div class="flex flex-col sm:flex-row gap-2 text-xl items-center">
      <router-link :to="{ name: 'PrivacyPolicy' }" active-class="border-b-textPrimary border-b-2">Privacy Policy</router-link>
      <span class="hidden sm:inline">|</span>
      <router-link :to="{ name: 'TermsOfService' }" active-class="border-b-textPrimary border-b-2">Terms of Service</router-link>
      <span class="hidden sm:inline">|</span>
      <router-link :to="{ name: 'ContactPage' }" active-class="border-b-textPrimary border-b-2">Contact</router-link>
    </div>
    <div class="text-xl mt-2 sm:mt-0">Copyright © 2025</div>
  </footer>
</template>

<style scoped>
footer {
  background: #fafafa;
}
</style>
