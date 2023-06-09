<!-- watchers are used to do something when watch data change -->

<template>
  <h1>Volume can be 0 - 20</h1>
  <p>Your current volumne - {{ volume }}</p>
  <button @click="volume++">Increase</button>
  <button @click="volume--">Decrease</button>
  <input type="text" v-model="movie" />
  <input type="text" v-model="movieInfo.actor" />
  <input type="text" v-model="movieInfo.movieName" />
</template>

<script>
export default {
  data() {
    return {
      volume: 0,
      movie: "Batman",
      movieInfo: {
        actor: "",
        movieName: "",
      },
    };
  },
  watch: {
    volume(newVolume, oldVolume) {
      if (newVolume >= 16 && newVolume > oldVolume) {
        alert(
          "Listening to a high volume for a long time may danger your hearing."
        );
      }
    },
    movie: {
      handler() {
        console.log(
          `You are calling movie api with movie name = ${this.movie}`
        );
      },
      immediate: true,
      // basically watcher run when watched data change but when immediate option Set
      // to true it runs immediate doesn's wait to change watched data
    },
    movieInfo: {
      handler() {
        console.log(
          `You are calling movie api with actorName = ${this.movieInfo.actor} and title = ${this.movieInfo.movieName}`
        );
      },
      deep: true,
      //when watching object we need to set deep option.If we dont set this option vue will not watch object property change
      //when we change object property we are not actually change object
    },
  },
};
</script>
