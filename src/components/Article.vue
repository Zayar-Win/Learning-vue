<template>
  <div>
    <h1 v-bind="$attrs">{{ title }}</h1>
    <h4>Liked - {{ likes }}</h4>
    <p>Published - {{ isPublished ? "Yes" : "No" }}</p>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    likes: {
      type: Number,
    },
    isPublished: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {};
  },
  inheritAttrs: false, //this option will disable inheritance non prop property
};
</script>

<style scoped></style>
