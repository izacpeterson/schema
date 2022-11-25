<script setup>
</script>

<template>
  <main class="flex flex-col p-5">
    <label for="" class="m-2">Name: <input type="text" v-model="schema.name" class="bg-gray-200 p-1"></label>
    <label for="" class="m-2">Total Time: <input type="text" v-model="schema.totalTime" class="bg-gray-200 p-1"></label>
    <div v-for="step in schema.step" class="m-2">
      <label for="" class="m-2">Step Name: <input type="text" v-model="step.name" class="bg-gray-200 p-1"></label>
      <label for="" class="m-2">Step Text: <input type="text" v-model="step.text" class="bg-gray-200 p-1"></label>
      <label for="" class="m-2">Step Image URL: <input type="text" v-model="step.image" class="bg-gray-200 p-1"></label>
    </div>
    <button @click="addStep" class="bg-blue-500">Add Step</button>
    <pre>{{ schema }}</pre>
  </main>
</template>
<script>
export default {
  data() {
    return {
      // data
      schema: {
        "@context": "https://schema.org/",
        "@type": "HowTo",
        step: []
      }
    }
  },
  methods: {
    addStep() {
      this.schema.step.push({ "@type": "HowToStep" })
    }
  }
}
</script>
