<template>
    <div class="container">
        <h2 class="film-title">I Film </h2>
        <div class="results-container">
            <!-- <font-awesome-icon :icon="['far', 'star']" />
            <font-awesome-icon :icon="['fas', 'star']" /> -->
        <div  class="results-container">
            <Film  v-for="(film, index) in films" :key="index" :info="film" />
        </div>

        </div>
        <h2>Le serie TV</h2>
        <div class="results-container">
            <Film v-for="(film, index) in tvSeries" :key="index" :info="film" />
        </div>
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

<style lang="scss">

h2 {
font-size: 40px;
margin: 30px 0;
}

.results-container {
    display: flex;
    flex-wrap: wrap;
    
    li {
        list-style: none;
    }
}


</style>