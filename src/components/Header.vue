<template>
    <header>
        <div class="boolflix-logo">
            <img src="../assets/img/BooFlix-logo.png" alt="">
        </div>
        <form class="search-bar">
            <input type="text" v-model="inputText" placeholder="Cerca un titolo...">
            <button class="search-btn" @click.prevent="$emit('search', inputText)">Cerca</button>
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
    background: linear-gradient(180deg, rgba(0,0,0,1) 1%, rgba(20,20,20,1) 50%, rgba(0,0,0,1) 99%);
    // background-color: #000;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 10px;

    .boolflix-logo {
            
            img {
                height: 75px;
            }
    }

    .search-bar {
        margin-right: 10px;
        
        input {
            border-radius: 0;
            border: none;
            padding: 0 5px;
            line-height: 40px;
            width: 200px;
        }

        .search-btn {
            background-color: #db202c;
            color: #fff;
            padding: 10px 15px;
            border: none;
            margin-left: 10px;
            font-size: 18px;
            cursor: pointer;
        }
    }
}

</style> 