<template>
    <h1>New patient</h1>
    <div class="container">
        <div class="form">
            <label>
                Name:
                <input v-model="name"/>
            </label>
            <label>
                Last name:
                <input v-model="lastName"/>
            </label>
            <label>
                Phone:
                <input v-model="phone" max-length="9" min-length="9"/>
            </label>
            <label>
                Birthdate:
                <input v-model="birthdate" type="date"/>
            </label>
            <label>
                Address:
                <input v-model="address"/>
            </label>
            <label>
                Record:
                <input v-model="record"/>
            </label>
        </div>
        <div class="card">
            <h3>Card:</h3>
            <div>{{fullName}}</div>
            <div>{{phone}}</div>
            <div>{{birthdate}}</div>
            <div>{{address}}</div>
            <div>{{record}}</div>
        </div>
    </div>
    <button v-on:click="savePatient">Save</button>
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
    fullName="";

    savePatient = () => {
        this.fullName = `${this.name} ${this.lastName}`;
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