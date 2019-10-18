<template>
    <div>
        <DrinkBanner :name="name" :category="category" :image="image" />
        <DrinkInfo :instructions="instructions" :ingredients="ingredients" :measurements="measurements" />
    </div>
</template>

<script>

import DrinkBanner from './DrinkBanner'
import DrinkInfo from './DrinkInfo'

export default {
    components: {
        DrinkBanner,
        DrinkInfo
    },
    props: ['ingredients', 'instructions', 'measurements', 'name', 'category', 'image']
}
</script>

<style>
    @media(min-width: 768px) {
        .banner {
            display: flex;
        }
    }
    ul {
        list-style: none;
        padding: 0;
    }
    .instructions {
        margin-top: 30px;
        padding: 20px;
    }
</style>