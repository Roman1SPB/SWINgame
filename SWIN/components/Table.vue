<template>
    <div id="app">
        <div class="wrapper">
            <div class="card_place" v-for="card in computer_cards">
                <img class="card_icon" :src="card.icon_path">
            </div>
        </div>
        <div class="wrapper">
            <div class="card_place" v-for="card in player_cards">
                <button><img class="card_icon" :src="card.icon_path"></button>
            </div>
        </div>
    </div>

    
</template>

<script>
export default {
    props: ['computer_cards', 'player_cards', 'id'],
}
</script>


<style>
#app {
    margin: 0;
    padding: 0;
    text-align: center;
}

.wrapper {
    margin-top: 20px;
}

.card_icon {
    width: 100px;
}

.card_place {
    display: inline;
    margin-left: 10px;
}
</style>