<template>
    <h1>New patient</h1>
    <input v-model="name"/>
    <input v-model="lastName"/>
    <input v-model="phone"/>
    <input v-model="birthdate"/>
    <input v-model="address"/>
    <input v-model="record"/>

    <div>
        Card:
        {{name + lastName}}
        {{phone}}
        {{birthdate}}
        {{address}}
        {{record}}
    </div>
</template>

<script lang="ts">
import {Vue} from 'vue-class-component';

export default class Patient extends Vue {
    name = "Thomas";
    lastName = "Sifuentes";
    phone = "";
    birthdate = "";
    address = "";
    record = "";
}
</script>