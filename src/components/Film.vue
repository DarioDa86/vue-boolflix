<template>
        <ul class="film-card">
            <li>
                <img v-if="info.poster_path != null" :src="`https://image.tmdb.org/t/p/w342${info.poster_path}`">
                <img v-else :src="`https://thumbs.dreamstime.com/b/punto-interrogativo-20881124.jpg`" alt="">
            </li>
            <li>{{info.title || info.name}}</li>
            <li>{{info.original_title || info.original_name}}</li>
            <li >{{info.original_language}} 
                <img :src="flag(info.original_language)">
            </li>
            <li>
                <span class="star"
                    v-for="(stars, index ) in starsNumber() " :key="index">
                    <font-awesome-icon :icon="['fas', 'star']" />
                </span>

                <span class="star-border" 
                    v-for="(stars, index ) in ( 5 - starsNumber()) " :key="index">
                    <font-awesome-icon :icon="['far', 'star']" />
                </span>
            </li>
        </ul>
</template>

<script>
export default {
    name: "Film",
    props: ['info'],
    data() {
        return {
            noFlag: [ 'iu', 'jv', 'kg', 'ki','te', 'tl', 'kj', 'gu', 'ii', 'ik', 'ml', 'mr',  'nn', 'nr', 'pi', 'ps', 'sa', 'nb', 'nd', 'ng', 'sw',  'tw']
        }
    },

    methods: {
        flag(flagCode) {
                if ( this.noFlag.includes(flagCode) ) {
                    return `https://upload.wikimedia.org/wikipedia/commons/thumb/e/ee/PACE-flag.svg/1200px-PACE-flag.svg.png`
                }   else {return `https://www.unknown.nu/flags/images/${flagCode}-100`}
                
            },
        starsNumber() {
            return Math.ceil(this.info.vote_average / 2);
        },
    }
}
</script>

<style>



</style>