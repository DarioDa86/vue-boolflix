<template>
    <header>
        <form>
            <input type="text" v-model="inputText" placeholder="Cerca un titolo...">
            <button @click.prevent="$emit('search', inputText)">Search</button>
        </form>
    </header>
</template>

<script>

export default {
    name: "Header",
    data() {
		return {
			inputText: ""
		}
	},

}
</script>

<style lang="scss">

Header{
    background-color: #000;
    height: 50px;
    display: flex;
    justify-content: flex-end;
    align-items: center;

    form {
        margin-right: 20px;
    }
}

</style> 