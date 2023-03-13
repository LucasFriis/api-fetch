<template>
<div v-for="result in apiResults" class="api-result">
    <div>
        <p>ID: {{result.id}}</p>
        <h3>{{result.title}}</h3>
        <p>Completed: {{result.completed}}</p>
    </div>
</div>
</template>

<script>
  export default {
    name: 'ApiResult',
    data() {
      return {
        apiResults: []
      }
    },
    methods: {
      async getData() {
        const apiResponse = await fetch("https://jsonplaceholder.typicode.com/todos");
        const res = await apiResponse.json();
        this.apiResults = res;
      }
    },
    mounted() {
        this.getData();
    }
  }
</script>

<style>

.api-result {
    background-color: rgba(0, 162, 255, 0.514);
    width: 300px;
    border-radius: 10px;
    padding: 16px;
    margin: 40px auto;
    box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.1);
}


</style>