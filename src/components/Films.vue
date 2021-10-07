<template>
    <div class=" container">
        <h2 class="film-title">I Film </h2>
        <font-awesome-icon :icon="['far', 'star']" />
        <font-awesome-icon :icon="['fas', 'star']" />

        <ul>
            <li v-for="(film, index) in films" :key="index">
                <Film :info="film" />
            </li>
        </ul>
        <h2>Le serie TV</h2>
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