<!-- <script setup lang="ts">
import { type Ref, ref } from 'vue'

const tasks: Ref<Array<{txt: string, done: boolean, date: number}>, Array<{txt: string, done: boolean, date: number}>> = ref([])
const newTaskName: Ref<string, string> = ref('')

const addNewTask = () => {
  tasks.value.push({
    txt: newTaskName.value,
    done: true,
    date: Date.now()
  })
  newTaskName.value = ''
}


</script>

<template>
  <p>Todo list</p>
  <form action="" v-on:submit.prevent="addNewTask">
    <input type="text" placeholder="new task" v-model="newTaskName"/>
    <button>Add</button>
  </form>
  <ul>
    <li v-for="task in tasks">
      <input type="checkbox" v-model="task.done"> {{ task.txt }} is {{ task.done }}
    </li>
  </ul>
</template>

<style scoped>
.txtbtn {
  border: none;
  background: none;
  padding: 0, 0, 0, 0;
}
</style> -->

<template>
  <div class="header">
    <!-- <h1>Hello App!</h1>
    <p><strong>Current route path:</strong> {{ $route.fullPath }}</p> -->
    <nav>
      <img class="logo" src="/public/favicon.ico" alt="logo" />
      <RouterLink class="navItem" to="/">Go to Home</RouterLink>
      <RouterLink class="navItem" to="/about">Go to About</RouterLink>
    </nav>
  </div>
    <main>
      <RouterView />
  </main>
</template>


<style lang="css" scoped>
.header {
  background-color: rgb(33, 33, 33);
  top: 0;
}

nav {
  display: flex;
  align-items: center;
  outline-color: gray;
  outline-style: double;
  outline-width: 1px;
  border-radius: 3px;
  transition: outline-color 0.25s ease-in-out;
}

nav:hover {
  outline-color: whitesmoke;
}

.navItem {
  margin-left: 15px;
}

.logo {
  width: 64px;
  height: 64px;
  margin-left: 8vw;
  margin-right: 4vw;
}

p {
  color: aliceblue;
}

</style>