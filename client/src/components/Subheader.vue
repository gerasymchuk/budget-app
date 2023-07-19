<script setup>
import TagSelect from "./TagSelect.vue";

const { title } = defineProps(["title"]);
</script>

<template>
  <div class="subheader">
    <h3>{{ title }}</h3>
    <div class="filters-wrapper">
      <TagSelect />
    </div>
  </div>
</template>

<style scoped>
.subheader {
  margin-bottom: 1rem;
}
</style>
