<template>
    <main class="flex flex-col p-5 items-start">
        <h2 class="text-2xl">FAQ Schema</h2>
        <div v-for="question in schema.mainEntity" class="m-2">
            <label for="" class="m-2">Question: <input type="text" v-model="question.name" class="bg-gray-200 p-1"></label>
            <label for="" class="m-2">Answer: <input type="text" v-model="question.acceptedAnswer.text" class="bg-gray-200 p-1"></label>
        </div>
        <button @click="addQuestion" class="bg-green-500 text-white p-2">Add Question</button>
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
                "@type": "FAQPage",
                mainEntity: []
            }
        }
    },
    methods: {
        addQuestion() {
            this.schema.mainEntity.push({ "@type": "Question", "name":'', "acceptedAnswer": { "@type": "Answer" } })
        }
    }
}
</script>