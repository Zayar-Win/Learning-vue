<template>
  <h1>{{ name }}</h1>
  <button @mouseover="changeName('awin', $event)">Change Name</button>
  <p>Count - {{ count }}</p>
  <button @click="increment(1)">Increment By 1</button>
  <button @click="increment(5)">Increment By 5</button>
  <button @click="decrement(1)">Decrement By 1</button>
  <button @click="decrement(5)">Decrement By 5</button>
</template>

<script>
export default {
  data() {
    return {
      name: "Zayarwin",
      count: 0,
    };
  },
  methods: {
    changeName(name, event) {
      this.name = name;
      console.log(event);
    },
    increment(num) {
      this.count += num;
    },
    decrement(num) {
      this.count -= num;
    },
  },
};
</script>
