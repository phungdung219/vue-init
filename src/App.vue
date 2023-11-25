<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import SidebarComp from './components/SidebarComp.vue';

</script>

<template>
  <header>
      <nav>
        <div class="flex justify-between items-center w-[230px] border-r border-black px-2">
          <img src="@/assets/images/logo1cash-01.png" alt="" srcset="">
          <button>
            <i class="ri-align-justify"></i>
          </button>
        </div>
      </nav>
  </header>
  <SidebarComp />
  <RouterView />
</template>

<style scoped>

</style>
