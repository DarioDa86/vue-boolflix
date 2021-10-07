<template>
        <ul class="film-card">
            <li>
                <img v-if="info.poster_path != null" :src="`https://image.tmdb.org/t/p/w342${info.poster_path}`">
                <img v-else  :src="`https://thumbs.dreamstime.com/b/punto-interrogativo-20881124.jpg`" alt="">
            </li>
            <li>{{info.title || info.name}}</li>
            <li>{{info.original_title || info.original_name}}</li>
            <li >{{info.original_language}} 
                <img :src="flag(info.original_language)">
            </li>
            <li>{{info.vote_average}}</li>
        </ul>
</template>

<script>
export default {
    name: "Film",
    props: ['info'],

    methods: {
        flag(flagCode) {
                return `https://www.unknown.nu/flags/images/${flagCode}-100`        
            },
    }
}
</script>

<style>

</style>