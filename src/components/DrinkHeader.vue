<template>
    <header>
        <div class="name-wrap" >
            <h2> {{ name }} </h2>
            <h4> {{ category }} </h4>
        </div>
        <div class="img-wrap" >
            <img class="drink-thumbnail" :src="image" alt="">
        </div>
    </header>
</template>

<script>
export default {
    props: ['name', 'image', 'category']
}
</script>

<style lang="css">
    .drink-thumbnail {
        width: 100%;
        max-width: 300px;
        border-radius: 50%;
        border: 4px solid;;
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
        header {
            display: flex;
        }
        .name-wrap {
            align-items: center;
        }
        .img-wrap {
            flex: 1;
        }        
    }
</style>