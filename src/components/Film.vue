<template>

        <ul class="film-card">
            <li>{{info.title}}</li>
            <li>{{info.original_title}}</li>
            <li>{{info.original_language}}</li>
            <li>{{info.vote_average}}</li>
        </ul>

</template>

<script>
export default {
    name: 'Film',
    props: {
        info: Object
    },
}
</script>

<style>

</style>