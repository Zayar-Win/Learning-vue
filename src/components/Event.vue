<template>
  <div>
    <h1>This is pop up modal.</h1>
    <input type="text" v-model.trim="name" />
    <button @click="$emit('close', name)">Close</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
    };
  },
  emits: {
    close: (name) => {
      if (name !== "") {
        return true;
      }
      return false;
    },
  },
};
</script>

<style scoped></style>
