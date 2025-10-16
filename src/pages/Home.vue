<script setup>

import LargeCardGrid from "@/components/LargeCardGrid.vue";
import SocialLinks from "@/components/SocialLinks.vue";
import InfoGrid from "@/components/InfoGrid.vue";
import {ref} from "vue";

const largeCards = ref([
  {
    href: '/articles/1',
    image: 'https://i.postimg.cc/tCVSZSQW/Slide-16-9-2.png',
    title: 'Условия и способы получения выплат за нарезки',
    description: 'Как получить выплаты, какой контент не допускается и многое другое'
  },
  {
    href: '/articles/2',
    image: 'https://i.postimg.cc/8zNRpt1C/Slide-16-9-1.png',
    title: 'Всё о расширениях',
    description: 'Не видите эмоуты? Тогда вам сюда'
  },
  {
    href: '/articles/3',
    image: 'https://i.postimg.cc/Kv6jw908/wplace-2025-10-11-23-06-07.png',
    title: 'WPlace Комьюнити',
    description: 'Всё о том что это такое и как в этом учавствовать'
  },

]);
</script>

<template>
    <SocialLinks />
    <InfoGrid />
    <LargeCardGrid :large-cards="largeCards"/>
</template>

<style scoped>

</style>