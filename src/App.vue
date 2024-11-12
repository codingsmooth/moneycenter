<script setup>
import { reactive, ref, computed } from 'vue'
import axios from 'axios'
import Header from './components/Header.vue'
import Budget from './components/Budget.vue'
import Categories from './components/Categories.vue'
import Tags from './components/Tags.vue'
import Search from './components/Search.vue'

const years = [
  {
    id: 2024,
    label: '2024'
  },
  {
    id: 2025,
    label: '2025'
  }
]

const accounts = [
  {
    id: 1,
    label: 'Commun CAV'
  },
  {
    id: 2,
    label: 'Perso CAV'
  }
]

const sections = [
  {
    id: 1,
    label: 'Budget'
  },
  {
    id: 2,
    label: 'Categories'
  },
  {
    id: 3,
    label: 'Tags'
  },
  {
    id: 4,
    label: 'Recherche'
  }
]

const accountId = ref(1)
const sectionId = ref(1)
const year = ref(2024)

const yearChanged = (selectedYear) => {
  //console.log('emit yearChange received')
  //console.log(selectedYear.value)
  year.value = selectedYear.value
  //console.log('Year changed')
}
const accountChanged = (selectedAccountId) => {
  //console.log('emit accountChange received')
  //console.log(selectedAccountId.value)
  accountId.value = selectedAccountId.value
  //console.log('Account changed')
}
const sectionChanged = (selectedSectionId) => {
  //console.log('emit sectionChange received')
  //console.log(selectedSectionId.value)
  sectionId.value = selectedSectionId.value
  //console.log('section changed')
}
</script>

<template>
  <Header :accountId="accountId" :years="years" :accounts="accounts" :sections="sections"  v-on:yearChange="yearChanged" v-on:accountChange="accountChanged"  v-on:sectionChange="sectionChanged" />
  <Budget :display="sectionId==1"/>
  <Categories :display="sectionId==2"/>
  <Tags :display="sectionId==3"/>
  <Search :display="sectionId==4"/>
</template>vite

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
