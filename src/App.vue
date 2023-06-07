<template>
  <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>
  <HelloWorld msg="Vite + Vue" />
  <h1
    v-bind:class="{
      male: isMale,
      new: isNew,
    }"
  >
    My Name is Zayarwin
  </h1>

  <p v-if="num === 0">This number is zero.</p>
  <p v-else-if="num < 0">This is negative number.</p>
  <p v-else-if="num > 0">This is positive number.</p>
  <p v-else>This is not a number</p>

  <template v-if="display">
    <h1>Hello world</h1>
    <h1>My name is Zayarwin</h1>
  </template>

  <p v-show="show">I am using v-show</p>

  <p v-for="name in names" :key="name">{{ name }}</p>

  <p v-for="name in fullNames" :key="name.first">
    {{ name.first }} {{ name.last }}
  </p>

  <h4 v-for="actor in actors" :key="actor.name">
    {{ actor.name }}
    <p v-for="movie in actor.movies" :key="movie">{{ movie }}</p>
  </h4>

  <template v-for="name in names" :key="name">
    <h1 v-if="name === 'Burce'">{{ name }}</h1>
  </template>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  components: {
    HelloWorld,
  },
  data() {
    return {
      name: "zayarwin",
      isNew: true,
      isMale: true,
      num: "hello",
      display: false,
      show: true,
      names: ["Burce", "Clark", "Diana"],
      fullNames: [
        {
          first: "Bruce",
          last: "Wayne",
        },
        {
          first: "Clark",
          last: "Kent",
        },
        {
          first: "Princess",
          last: "Diana",
        },
      ],
      actors: [
        {
          name: "Christian Bale",
          movies: ["Batman", "The Prestige"],
        },
        {
          name: "Di Caprio",
          movies: ["Titanic", "Inception"],
        },
      ],
    };
  },
};
</script>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.new {
  font-style: italic;
}
.male {
  color: green;
  font-size: 30px;
  font-weight: bold;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
