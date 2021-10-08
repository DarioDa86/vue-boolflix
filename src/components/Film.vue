<template>
        <div class="film-card">
            <div class="poster-box">
                <img v-if="info.poster_path != null" :src="`https://image.tmdb.org/t/p/w342${info.poster_path}`">
                <img v-else :src="`https://thumbs.dreamstime.com/b/punto-interrogativo-20881124.jpg`" alt="">
            </div>
            <ul class="film-info">
                <li><span class="txt-bold">Titolo: </span>{{info.title || info.name}}</li>
                <li><span class="txt-bold">Titolo originale: </span>{{info.original_title || info.original_name}}</li>
                <li ><span class="txt-bold">Lingua originale: </span>
                    <img class="flag-style" :src="flag(info.original_language)">
                </li>
                <li >
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
        </div>
</template>


<script>
export default {
    name: "Film",
    props: ['info'],
    data() {
        return {
            noFlag: ['iu', 'jv', 'kg', 'ki','te', 'tl', 'kj', 'gu', 'ii', 'ik', 'ml', 'mr',  'nn', 'nr', 'pi', 'ps', 'sa', 'nb', 'nd', 'ng', 'sw',  'tw']
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

<style lang="scss" scoped>

.film-card {
    width: calc(20% - 20px);
    margin: 10px;
    position: relative;

    .poster-box {
        width: 100%;
        overflow: hidden;
        border-radius: 5px;
        position: relative;

        img {
            border-radius: 5px;
            width: 100%;
            opacity: 1;
            transition: opacity .3s;

        }
        img:hover {
            opacity: 0;        
        }
    }

    .film-info {
        position: absolute;
        transition: 0.2s;
        opacity: 1;
        top: 10px;

        li {
            list-style: none;
            margin: 10px 5px;
    
            .txt-bold{
                font-weight: 600;
            }
    
            .flag-style {
                width: 40px;
                border-radius: 5px;
            }
    
            .star-border, .star {
                color: yellow;
            }
        }
    }

}

</style>