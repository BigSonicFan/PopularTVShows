<!--template for Header.vue-->
<template>
    <div class="header">
        <!--where the title from App.vue in Header code will be displayed-->
        <h1>{{theTitle}}</h1>
    </div>
</template>

<script>
//exporting name and prop for Header.vue
export default {
    name: 'Header',
    props: ['theTitle']
}
</script>