<!--template for Card.vue-->
<template>
    <div class="col" style="margin-left:auto; margin-right:auto; text-align:center; display:inline-block;">
        <div class="card" style="width: 18rem; display:inline-block;">
            <!--img code that includes a v-bind that connects the link for image-->
            <img class="card-img-top" v-bind:src="'https://image.tmdb.org/t/p/w500' + aShow.poster_path">
            <div class="card-body">
                <h5 class="card-title">{{aShow.name}}</h5>
                <p class="card-text">{{aShow.overview}}</p>
            </div>
        </div>
    </div>
</template>

<script>
//exporting name and prop for Card.vue
export default {
    name: 'Card',
    props: ['aShow']
}
</script>
<!--style code for classes card-body, and card-text-->
<style scoped>
    .card-body {
        margin:0px, 0px, 0px, 0px;
        padding-left:0px;
        padding-right:0px;
    }
    .card-text {
        height:250px;
    }
</style>