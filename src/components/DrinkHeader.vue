<template>
    <header class="header" >
        <h2 class="title" >Drinky-Drink</h2>
        <button @click="getDrinkData" class="new-drink-button" >New Drink <span>&#x21b7;</span> </button>   
    </header>
</template>

<script>
export default {
    methods: {
        getDrinkData: function() {
            this.$emit('getData');
        }
    }
}
</script>

<style lang="css">
    .title:hover {
        color: grey;
    }
    .title {
        transition: .7s;
        box-shadow: 10px 10px grey;
        padding: 10px;
        background: #000;
        color: #fff;
        width: 170px;
    }
    .new-drink-button {
        font-size: 14px;
        background: transparent;
        color: #000;
        border: 2px solid #000;
        padding: 10px;
        cursor: pointer;
        transition: 1s;
    }
    .new-drink-button:hover {
        background: #e2dfdb;
    }




    .drink-thumbnail {
        width: 100%;        
        max-height: 300px;
        max-width: 300px;
        border-radius: 50%;
        /* border: 1px solid;; */
        padding: 10px;
    }
    .name-wrap {
        flex-direction: column;
        align-items: center;      
    }
    .name-wrap,
    .img-wrap {
        display: flex;
        justify-content: center;
        flex: 1;
    }
    @media(min-width: 500px) {

        .name-wrap {
            align-items: center;
        }
        .img-wrap {
            flex: 1;
        }        
    }
</style>