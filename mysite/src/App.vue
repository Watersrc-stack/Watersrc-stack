<script setup lang="ts">
import { type Ref, ref } from 'vue'

const count: Ref<number, number> = ref(0)
var isSup: boolean = false

const increment = (event: Event) => {
  console.log(event)
  count.value++
  isSup = count.value > 9
}

const movies: Ref<string[], string[]> = ref(['Titanic', 'Ready player one', 'Le labyrinthe'])

const deleteMovie = (movie: string) => {
  movies.value = movies.value.filter((m) => m !== movie)
}

const movieName: Ref<string, string> = ref('')

const addMovie = (event: Event) => {
  movies.value.push(movieName.value)
  movieName.value = ''
  // event.preventDefault()
}
</script>

<template>
  <p
    v-bind:id="`p-count-${count}`"
    v-bind:style="{ color: count > 9 ? 'red' : count > 4 ? 'blue' : 'green' }"
  >
    Compteur: {{ count }}
  </p>
  <div v-if="isSup">Pov cookie clicker</div>
  <div v-else-if="count > 4">You know how to click on a button congrats</div>
  <div v-else>Too bad</div>
  <button v-on:click="increment">inc</button>

  <hr />
  <form action="" v-on:submit.prevent="addMovie">
    <input type="text" placeholder="new film" v-model="movieName" />
    <button>Add</button>
  </form>

  <ul>
    <li v-for="mv in movies" v-bind:key="mv">
      {{ mv }}<button class="txtbtn" v-on:click="deleteMovie(mv)">&#128465;</button>
    </li>
  </ul>
</template>

<style scoped>
.txtbtn {
  border: none;
  background: none;
  padding: 0, 0, 0, 0;
}
</style>
