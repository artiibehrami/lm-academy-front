<script setup>
import HeaderDefault from '@/components/default/general/HeaderDefault.vue'
import FooterDefault from '@/components/default/general/FooterDefault.vue'
</script>

<template>
  <main class="px-4">
    <!-- header -->
    <HeaderDefault />
    <!-- end header -->

    <!-- content -->
    <router-view class="wrapper min-h-[80vh]" />
    <!-- end content -->
    <FooterDefault />
  </main>
</template>
