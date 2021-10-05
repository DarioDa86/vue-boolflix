<template>
    <div class="films">
        <Film :info="elm"/>
    </div>
</template>

<script>
import Film from './Film.vue'

export default {
    name: 'films',
    props: ['transferFilms'],
    components: {
        Film
    }

}
</script>

<style>

</style>