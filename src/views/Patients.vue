<template>
    <h1>Patients</h1>
    <Card v-for="item in items" :key="item.name" :msg="item.name + ' ' + item.last_name" />
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
    
    fetchData = () => {
        fetch('http://localhost:5000/patients')
        .then(response => response.json())
        .then(data => this.items = data.data);
    };

    async created(){
    this.fetchData();
    }
} 

</script>