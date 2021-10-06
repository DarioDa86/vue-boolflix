<template>
    <ul  class="films-container">
        <li >
            <Film :info="film" v-for="(film, index) in films" :key="index"/>
        </li>
    </ul>
</template>

<script>
import Film from './Film.vue'

export default {
    name: 'Films',
    props: ['films'],
    components: {
        Film
    }

}
</script>

<style>

</style>