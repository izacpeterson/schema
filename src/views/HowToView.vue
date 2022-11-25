<script setup>
</script>

<template>
  <main class="flex flex-col p-5 items-start">
    <h2 class="text-2xl">How To Schema</h2>
    <label for="" class="m-2">Name: <input type="text" v-model="schema.name" class="bg-gray-200 p-1"></label>
    <label for="" class="m-2">Total Time: <input type="text" v-model="schema.totalTime" class="bg-gray-200 p-1"></label>
    <div v-for="step in schema.step" class="m-2">
      <label for="" class="m-2">Step Name: <input type="text" v-model="step.name" class="bg-gray-200 p-1"></label>
      <label for="" class="m-2">Step Text: <input type="text" v-model="step.text" class="bg-gray-200 p-1"></label>
      <label for="" class="m-2">Step Image URL: <input type="text" v-model="step.image" class="bg-gray-200 p-1"></label>
    </div>
    <button @click="addStep" class="bg-blue-500 text-white p-2">Add Step</button>
  </main>
  <pre class="bg-gray-200">{{`<script type="application/ld+json">`}} {{ schema }} {{`</script>`}} </pre>
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
