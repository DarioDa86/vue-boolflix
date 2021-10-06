<template>

        <div  class="films-container">
            <Film :info="film" v-for="(film, index) in films" :key="index"/>
        </div>
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