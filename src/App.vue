<script setup lang="ts">
import { ref } from 'vue'

const listItems = ref([])
function onInputChange(event) {
  listItems.value.push(event.target.value)
}
function addItem() {}
// return { listItems, addItem, onInputChange }
</script>

<template>
  <div class="flex justify-center items-center">
    <div class="w-96 border rounded-2xl flex flex-col justify-center items-center pb-8 pt-3 gap-3">
      <div class="flex flex-col w-full justify-center items-center">
        <span>Todo</span>
        <span>Add your daily things here!</span>
      </div>
      <textarea class="border w-72 rounded pl-2" @change="onInputChange"></textarea>
      <button class="border rounded px-2" @click="addItem">Add</button>
    </div>
  </div>

  <div class="border rounded-2xl ml-10">
    <ul>
      <li v-for="item in listItems" :key="item">{{ item }}</li>
    </ul>
  </div>
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
