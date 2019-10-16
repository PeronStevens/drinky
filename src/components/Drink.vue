<template>
    <div class="container" >
        <h2 class="title" >Sippy Cup</h2>
        <button @click="getDrinkData" class="new-drink-button" >New Drink</button>   
        <DrinkHeader :name="drinkName" :category="drinkCategory" :image="drinkImgUrl" />
        <DrinkContent :instructions="drinkInstructions" :measurements="measures" :ingredients="ingredients" />
    </div>
</template>

<script>

import axios from 'axios';
import DrinkHeader from './DrinkHeader'
import DrinkContent from './DrinkContent'

export default {
    components: {
        DrinkHeader,
        DrinkContent
    },
    data: function() {
        return {
            drinkData: {},
            drinkName: '',
            drinkImgUrl: '',
            drinkCategory: '',
            drinkInstructions: '',
            ingredients: [],
            measures: []
        }
    },
    mounted: function() {
        this.getDrinkData();
    },
    methods: {
        getDrinkData: function() {
            this.ingredients = [];
            this.measures = [];

            axios.get('https://www.thecocktaildb.com/api/json/v1/1/random.php')
            .then((response) => {            
                this.drinkData = response.data.drinks[0];
                // console.log(response.data.drinks[0]);
            })            
        }
    },
    watch: {
        drinkData: function() {
            for (let [key, value] of Object.entries(this.drinkData)) {
                if (value) {
                    if (key.includes('strIngredient')) this.ingredients.push(value)
                    if (key.includes('strMeasure')) this.measures.push(value)
                    if (key == 'strDrinkThumb') this.drinkImgUrl = value;
                    if (key == 'strDrink') this.drinkName = value;
                    if (key == 'strCategory') this.drinkCategory = value;
                    if (key == 'strInstructions') this.drinkInstructions = value;
                }
            }
        }
    }
}
</script>

<style scoped>
    .container {
        margin: auto;
        max-width: 768px;


    font-family: 'Playfair Display', serif;

    }
    .title:hover {
        color: grey;
    }
    .title {
        transition: .7s;
        box-shadow: 10px 10px grey;
        padding: 10px;
        background: #000;
        color: #fff;
        width: 120px;
    }
    .new-drink-button {
        background: #7b7b7b;
        color: #fff;
        border: none;
        padding: 10px;
        cursor: pointer;
    }
    .new-drink-button:hover {
        background: #353535;
    }
</style>