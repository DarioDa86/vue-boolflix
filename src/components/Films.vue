<template>
    <div class="films-container">
        <ul>
            <li v-for="(film, index) in films" :key="index">
                <Film :info="film" />
            </li>
        </ul>
        <ul>
            <li v-for="(film, index) in tvSeries" :key="index">
                <Film :info="film" />
            </li>
        </ul>
    </div>
</template>

<script>
import Film from './Film.vue'

export default {
    name: 'Films',
    props: ['films', 'tvSeries'],
    components: {
        Film
    }

}
</script>

<style>

</style>