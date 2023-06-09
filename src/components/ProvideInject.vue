<template>
  <div>My name is {{ username }}</div>
</template>

<script>
export default {
  data() {
    return {};
  },
  inject: ["username"],
};
</script>

<style scoped></style>
