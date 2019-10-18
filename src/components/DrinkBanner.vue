<template>
    <div class="banner" >
        <div class="name-wrap" >
            <h1> {{ name }} </h1>
            <h4> {{ category }} </h4>
        </div>
        <div class="img-wrap" >
            <img class="drink-thumbnail" :src="image" alt="">
        </div>
    </div>
</template>

<script>
export default {
    props: ['name', 'category', 'image']
}
</script>