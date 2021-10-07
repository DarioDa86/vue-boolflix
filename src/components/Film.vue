<template>
        <ul class="film-card">
            <li>
                <img v-if="info.poster_path != null" :src="`https://image.tmdb.org/t/p/w342${info.poster_path}`">
                <img v-else :src="`https://thumbs.dreamstime.com/b/punto-interrogativo-20881124.jpg`" alt="">
            </li>
            <li>{{info.title || info.name}}</li>
            <li>{{info.original_title || info.original_name}}</li>
            <li >{{info.original_language}} 
                <img v-if="info.original_language != null" :src="flag(info.original_language)">
                <img v-else src="`https://static.vecteezy.com/ti/vettori-gratis/p1/554325-icona-di-vettore-del-fumetto-del-punto-interrogativo-gratuito-vettoriale.jpg`" alt="">
            </li>
            <li>
                <div v-for="(stars, index ) in starsNumber() " :key="index">
                    <font-awesome-icon :icon="['fas', 'star']" />
                </div>

                <div v-for="(stars, index ) in ( 5 - starsNumber()) " :key="index">
                    <font-awesome-icon :icon="['far', 'star']" />
                </div>
            </li>
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
        starsNumber() {
            return Math.ceil(this.info.vote_average / 2);
        },
    }
}
</script>

<style>

</style>