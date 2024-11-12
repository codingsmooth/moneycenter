<script setup>
import { ref, onMounted } from 'vue'

defineProps({
  accountId: Number,
  years: Array,
  accounts: Array,
  sections: Array
})

const selectedAccountId = ref(1)
const selectedSectionId = ref(1)
const selectedYear = ref(2024)
const emit = defineEmits(['yearChange', 'accountChange', 'sectionChange'])

onMounted(() => {
  console.log('Header loaded')
})

const setYear = () => {
  /*
  console.log('Year selected')
  console.log(selectedYear.value)
  console.log('emit yearChange')
  */
  emit('yearChange', selectedYear)
}

const setAccountId = () => {
  /*
  console.log('Account selected')
  console.log(selectedAccountId.value)
  console.log('emit accountChange')
  */
  emit('accountChange', selectedAccountId)
}

const setSectionId = () => {
  /*
  console.log('Section selected')
  console.log(selectedSectionId.value)
  console.log('emit sectionChange')
  */
  emit('sectionChange', selectedSectionId)
}
</script>

<template>
  <div class="card">
    <select v-model="selectedYear" @change="setYear">
      <option v-for="year in years" :value="year.id">
        {{ year.label }}
      </option>
    </select>
    <select v-model="selectedAccountId" @change="setAccountId">
      <option v-for="account in accounts" :value="account.id">
        {{ account.label }}
      </option>
    </select>
    <select v-model="selectedSectionId" @change="setSectionId">
      <option v-for="section in sections" :value="section.id">
        {{ section.label }}
      </option>
    </select>
  </div>
</template>

<style scoped>

</style>