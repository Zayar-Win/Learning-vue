<template>
  <div v-for="name in names" :key="name.firstName">
    <slot :firstName="name.firstName" :lastName="name.lastName" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      names: [
        { firstName: "zayar", lastName: "win" },
        { firstName: "rar", lastName: "zar" },
        { firstName: "aung", lastName: "khant" },
      ],
    };
  },
};
</script>

<style scoped></style>
