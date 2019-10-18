<template>
    <div class="instructions" >
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
    props: ['instructions', 'ingredients', 'measurements']
}
</script>