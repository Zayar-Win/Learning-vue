<template>
  <p>My FullName is {{ firstName }} {{ lastName }}</p>
  <p>My FullName using computed property is {{ fullName }}</p>
  <button @click="changeFullName('a win')">Change name</button>
  <p>
    The total price of my desk setup is
    {{ items.reduce((prev, curr) => prev + curr.price, 0) }}
  </p>
  <p>
    My total price of my desk setup using computed property is {{ totalPrice }}
  </p>
  <!-- if we use method instead of computed property when component rerender computed property use cached value instead of recalculating.
  but method recalcalated  -->
  <p>My total price of my desk setup using method is {{ getTotalPrice() }}</p>
  <input type="text" v-model="text" />
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
      text: "",
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
  methods: {
    getTotalPrice() {
      console.log("run getTotalPrice method");
      return this.items.reduce((prev, curr) => prev + curr.price, 0);
    },
    changeFullName(name) {
      this.fullName = name;
    },
  },
  computed: {
    fullName: {
      get() {
        return `${this.firstName} ${this.lastName}`;
      },
      set(value) {
        let names = value.split(" ");
        this.firstName = names[0];
        this.lastName = names[1];
      },
    },
    totalPrice() {
      console.log("run totalPrice computed method");
      return this.items.reduce((prev, curr) => prev + curr.price, 0);
    },
  },
};
</script>
