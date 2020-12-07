<!--template for CardList.vue-->
<template>
    <div>
        <p v-for="tvShow in tvShowList" v-bind:key="tvShow.id">
            <!--where the code from Card.vue will be displayed-->
            <Card v-bind:aShow="tvShow" />
        </p>
    </div>
</template>

<script>
//importing Card.vue
import Card from '../components/Card.vue'
//exporting name, props, and component for CardList.vue
export default {
    name: "CardList",
    props: ['theTitle', 'tvShowList'],
    components: {
        Card
    }
}
</script>