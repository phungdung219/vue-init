<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import { FwbSidebar, FwbSidebarItem, FwbSidebarDropdownItem } from 'flowbite-vue'
import { ref } from 'vue';

const items = ref([
  {
    title: "Cầm đồ",
    link: '/',
    isDropdown: false,
  },
  {
    title: "Tín chấp",
    link: '/',
    isDropdown: false,
  },
  {
    title: "Trả góp",
    link: '/',
    isDropdown: false,
  },
  {
    title: "Quản lí cửa hàng",
    link: '/',
    isDropdown: true,
    dropdownItems: [
      {
        title: "Tổng quát chuỗi cửa hàng",
        link: '/',
      },
      {
        title: "Thông tin chi tiết cửa hàng",
        link: '/',
      },
      {
        title: "Danh sách cửa hàng",
        link: '/',
      },
      {
        title: "Cấu hình hàng hóa",
        link: '/',
      },
      {
        title: "Nhập tiền quỹ đầu ngày",
        link: '/',
      },
    ]
  },
  {
    title: "Quản lí thu chi",
    link: '/',
    isDropdown: true,
    dropdownItems: [
      {
        title: "Chi hoạt động",
        link: '/',
      },
      {
        title: "Thu hoạt động",
        link: '/',
      },
    ]
  },
  {
    title: "Quản lí nguồn vốn",
    link: '/',
    isDropdown: false,
  },
  {
    title: "Quản lí nhân viên",
    link: '/',
    isDropdown: true,
    dropdownItems: [
      {
        title: "Danh sách nhân viên",
        link: '/',
      },
      {
        title: "Phân quyền nhân viên",
        link: '/',
      },
    ]
  },
])
</script>

<template>
  <fwb-sidebar>
    <template v-for="item in items" :key="item.title">
      <fwb-sidebar-item 
        v-if="!item.isDropdown"
        :link="item.link"
      >
        <template #icon>
          <i class="ri-mac-line"></i>
        </template>
        <template #default >{{ item.title }}</template>
      </fwb-sidebar-item>
      <fwb-sidebar-dropdown-item v-else>
        <template #icon>
          <i class="ri-mac-line"></i>
        </template>
        <template #trigger> {{ item.title }} </template>
        <template #default>
          <fwb-sidebar-item class="pl-6 text-sm" 
            v-for="dropdownItem in item.dropdownItems" 
            :key="dropdownItem.title"
            :link="dropdownItem.link"
          > 
            <i class="ri-arrow-right-s-line"></i>
            {{ dropdownItem.title }}  
          </fwb-sidebar-item>
        </template> 
      </fwb-sidebar-dropdown-item>
    </template>
    
  </fwb-sidebar>

</template>

<style scoped>

</style>
