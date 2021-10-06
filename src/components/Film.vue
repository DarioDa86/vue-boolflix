<template>
        <ul class="film-card">
            <li>{{info.title || info.name}}</li>
            <li>{{info.original_title || info.original_name}}</li>
            <li >{{info.original_language}} 
                <img :src="flag(info.original_language)" alt="">
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
            }
    }
}
</script>

<style>

</style>