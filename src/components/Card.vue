<template>
    <div class="card">
        <h3>This is a Card</h3>
        <div>{{ msg }}</div>
    </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
    props: {
        msg: String,
    }
})

export default class Card extends Vue {
    msg!: string;
}
</script>

<style lang="scss" scoped>
    .card {
        padding: 20px;
        margin: 20px;
        border: 1px solid #ccc;
        border-radius: 5px;
        position: relative;
        display: flex;
        flex-direction: column;
        min-width: 0;
        word-wrap: break-word;
        width: 20%;
        cursor: pointer;
    }
    .card:hover {
        background-color: #f6f6f6;
    }
</style>