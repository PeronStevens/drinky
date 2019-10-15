<template>
    <div class="content" >
        <h3>Instructions</h3>
        <p>            
            {{ instructions }}
        </p>
        <ul>
            <h3>Ingredients</h3>
            <li v-for="(ingredient, index) in ingredients" :key="index" >
                {{ measurements[index] }} {{ ingredient }}
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    props: ['ingredients', 'instructions', 'measurements']
}
</script>

<style>
    ul {
        list-style: none;
        padding: 0;
    }
    .content {
        margin-top: 30px;
        padding: 20px;
    }
</style>