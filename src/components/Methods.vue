<template>
  <p>Add method : {{ add(1, 2, 3) }}</p>
  <p>Add method : {{ add(5, 7, 3) }}</p>
  <p>Multiply method : {{ multiply(30) }}</p>
</template>

<script>
export default {
  data() {
    return {
      multiplyNumber: 4,
    };
  },
  methods: {
    add(a, b, c) {
      return a + b + c;
    },
    multiply(number) {
      return number * this.multiplyNumber;
    },
  },
};
</script>
