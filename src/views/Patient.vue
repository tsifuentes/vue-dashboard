<template>
    <h1>New patient</h1>
    <div class="container">
        <div class="form">
            <label>
                Name:
                <input v-model="patient.name"/>
            </label>
            <label>
                Last name:
                <input v-model="patient.lastName"/>
            </label>
            <label>
                Phone:
                <input v-model="patient.phone" max-length="9" min-length="9"/>
            </label>
            <label>
                Birthdate:
                <input v-model="patient.birthdate" type="date"/>
            </label>
            <label>
                Address:
                <input v-model="patient.address"/>
            </label>
            <label>
                Record:
                <input v-model="patient.record"/>
            </label>
        </div>
        <div class="card">
            <h3>Card:</h3>
            <div>{{patient.fullName}}</div>
            <div>{{patient.phone}}</div>
            <div>{{patient.birthdate}}</div>
            <div>{{patient.address}}</div>
            <div>{{patient.record}}</div>
        </div>
    </div>
    <button v-on:click="savePatient">Save</button>
</template>

<script lang="ts">
import {Vue} from 'vue-class-component';

export default class Patient extends Vue {
    patient = {
        name: "",
        lastName: "",
        phone: "",
        birthdate: "",
        address: "",
        record: "",
        fullName: "",
    }

    savePatient = async () => {
        this.patient.fullName = `${this.patient.name} ${this.patient.lastName}`;
        await fetch("http://localhost:5000/patient", {
            method: "POST",
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify(this.patient),
        });

    };
}
</script>

<style lang="scss">
    .container {
        display: flex;
        max-width: 50%;
        margin: 0 auto;
    }
    .form {
        width: 60%;
    }
    .card {
        border-radius: 10px;
        border: 1px solid #ccc;
        text-align: left;
        padding: 20px;
        width: auto;
        display: table-cell;
        > h3 {
            margin-top: 0;
        }
    }
    label {
        display: block;
        text-align: left;
        margin: 15px;
        > input {
            display: block;
            border: 1px solid #ccc;
            padding: 10px;
            border-radius: 5px;
        }
    }

    button {
        border-radius: 10px;
        background-color: blue;
        color: #fff;
        font-weight: bold;
        padding: 10px 20px;
        border: 1px solid blue;
    }
</style>