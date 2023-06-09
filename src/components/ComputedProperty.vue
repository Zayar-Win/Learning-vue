<template>
  <p>My FullName is {{ firstName }} {{ lastName }}</p>
  <p>My FullName using computed property is {{ fullName }}</p>

  <p>
    The total price of my desk setup is
    {{ items.reduce((prev, curr) => prev + curr.price, 0) }}
  </p>
  <p>
    My total price of my desk setup using computed properth is {{ totalPrice }}
  </p>
  <button
    @click="
      items.push({
        id: items[items.length - 1].id + 1,
        name: 'New item',
        price: Math.floor(Math.random() * 300),
      })
    "
  >
    Add Item
  </button>
  <pre>
    {{ JSON.stringify(items, null, 2) }}
  </pre>
</template>

<script>
export default {
  data() {
    return {
      firstName: "Zayar",
      lastName: "Win",
      items: [
        {
          id: 1,
          name: "Monitar",
          price: 300,
        },
        {
          id: 2,
          name: "Keyboard",
          price: 100,
        },
        {
          id: 3,
          name: "Mouse",
          price: 50,
        },
      ],
    };
  },
  computed: {
    fullName() {
      return `${this.firstName} ${this.lastName}`;
    },
    totalPrice() {
      return this.items.reduce((prev, curr) => prev + curr.price, 0);
    },
  },
};
</script>
