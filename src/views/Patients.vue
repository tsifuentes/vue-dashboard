<template>
    <h1>Patients</h1>
    <router-link to="/new-patient">New Patient</router-link>
    <button v-on:click="show">{{buttonText}}</button>
    <div v-if="seen">
        <Card v-for="item in items" :key="item.name" :msg="item.name + ' ' + item.last_name" />
    </div>
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
    seen = true;
    items = [];
    buttonText = "Hide";
    
    show = () => {
        this.seen = !this.seen;
        this.buttonText = !this.seen ? "Show": "Hide";
    };

    fetchData = async () => {
        await fetch('http://localhost:5000/patient?mem=true')
        .then(response => response.json())
        .then(data => this.items = data.data);
    };

    async created(){
        this.fetchData();
    }
} 

</script>