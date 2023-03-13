<template>
  <div class="home">
    <img style="height: 100px;" alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Resultat fra ekstern API"/>
    <ApiResult />
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import HelloWorld from '@/components/HelloWorld.vue';
import ApiResult from '@/components/ApiResult.vue'; // @ is an alias to /src

@Options({
  components: {
    HelloWorld,
    ApiResult
  },
})
export default class HomeView extends Vue {}
</script>
