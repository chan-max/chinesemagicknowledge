<template>
  {{ data }}
</template>

<script setup>
import { useRoute } from "vue-router";
import Api from "@/common/api/axios";

let route = useRoute();

let id = route.params.id;

let data = ref();

async function init() {
  let res = await Api.getDreamById(id);
  data.value = res;
}

init();
</script>
