<template>
    <Header>
        <form action="">
            <input type="text"  placeholder="Cerca un titolo..." v-model="inputText">
            <button type="submit" class="btn btn-primary mx-3" @click.prevent="$emit('search', inputText)">Search</button>
            
        </form>
    </Header>
</template>

<script>

export default {
    data() {
		return {
			inputText: ""
		}
	},

}
</script>

<style lang="scss" scoped>

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