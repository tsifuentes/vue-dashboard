<template>
  <div class="home">
    <HelloWorld msg="Welcome to My first Vue app!" />
    <div class="container">
    <Card msg="First Card"/>
    <Card msg="Second Card"/>
    <Card msg="Third Card"/>
    <Card msg="Fourth Card"/>
    <Card msg="Fifth Card"/>
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import HelloWorld from "@/components/HelloWorld.vue"; // @ is an alias to /src
import Card from "@/components/Card.vue";

@Options({
  components: {
    HelloWorld,
    Card,
  },
})
export default class Home extends Vue {}
</script>

<style lang="scss" scoped>
.container {
  display: flex;
}
</style>
