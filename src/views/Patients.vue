<template>
    <h1>Patients</h1>
    <Card v-for="item in items" :key="item.message" :msg="item.message" />
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import Card from '@/components/Card.vue';

@Options({
    components: {
        Card,
    },
})
export default class Patients extends Vue {
    items = [{message: 'xxxxx'}, {message: 'xxxxx'}];
} 

</script>