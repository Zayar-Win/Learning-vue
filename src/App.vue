<template>
  <!-- <h1
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
  </template> -->

  <!-- <Methods /> -->
  <!-- <EventHandling /> -->
  <!-- <FormHandling /> -->
  <!-- <ComputedProperty /> -->
  <!-- <Watchers /> -->
  <!-- <Article
    id="article"
    title="This is blog title"
    :likes="100"
    :isPublished="true"
  /> -->
  <!-- <ProvideInject /> -->
  <!-- <Event @close="closePopup" v-if="open" /> -->
  <!-- <button @click="open = true">Open Popup</button> -->
  <!-- <Input v-model="name" /> -->
  <!-- {{ name }} -->
  <!-- <Card>
    <template v-slot:header>
      <p>This is card Title</p>
    </template>
    <template v-slot:default>
      <p>This is card body</p>
    </template>
    <template v-slot:footer>
      <p>This is card Footer</p>
    </template>
  </Card> -->
  <NameList>
    <template #default="slotProps">
      <h3>{{ slotProps.firstName }} {{ slotProps.lastName }}</h3>
    </template>
  </NameList>
</template>

<script>
import Methods from "./components/Methods.vue";
import EventHandling from "./components/EventHandling.vue";
import FormHandling from "./components/FormHandling.vue";
import ComputedProperty from "./components/ComputedProperty.vue";
import Watchers from "./components/Watchers.vue";
import Article from "./components/Article.vue";
import ProvideInject from "./components/ProvideInject.vue";
import Event from "./components/Event.vue";
import Input from "./components/Input.vue";
import Card from "./components/Card.vue";
import NameList from "./components/NameList.vue";
export default {
  components: {
    Methods,
    EventHandling,
    FormHandling,
    ComputedProperty,
    NameList,
    Card,
    Watchers,
    Article,
    ProvideInject,
    Event,
    Input,
  },
  data() {
    return {
      name: "zayarwin",
      isNew: true,
      isMale: true,
      open: false,
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
  methods: {
    closePopup(name) {
      this.open = false;
      console.log(name);
    },
  },
  provide() {
    return {
      username: this.name,
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
