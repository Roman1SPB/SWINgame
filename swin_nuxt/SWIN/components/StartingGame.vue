<template>
    <body>
        <button @click="start" id="startButton">Start</button>
    </body>
</template>


<script>

export default {
    data() {
        return {
            card_values: ['6', '7', '8', '9', '10', "Jack", "Queen", "King", "Ace"],
            card_suits: ["spades", "heart-card", "diamond", "club-card"],
            cards_array: [],
            computer_cards: [],
            player_cards: [],
            id: 0,

            cardTemplate: {
                value: String,
                suit: String,
                id: Number,
                icon_path: String,
            }
        }
    },

    methods: {
        start() {
            for (let suit_ of this.card_suits) {
                for (let value_ of this.card_values) {
                    let icon_path = "/public/Playingcardsicons/" + suit_ + value_.toString() + ".png";
                    this.cardTemplate = {
                        value: value_,
                        suit: suit_,
                        id: this.id,
                        icon_path: icon_path,
                    }
                    this.cards_array.push(this.cardTemplate);
                    this.id++;
                }
            }

            this.cards_array = this.cards_array.sort(() => Math.random() - 0.5);
            this.computer_cards = this.cards_array.slice(0, 6);
            this.player_cards = this.cards_array.slice(6, 12);
            this.cards_array = this.cards_array.slice(12, 36);
            //console.log(this.computer_cards);
            //console.log(this.player_cards);
            startButton.style.display = 'none';
            this.$emit('show-table', {
                computer_cards: this.computer_cards,
                player_cards: this.player_cards,
            });
            return;
        }
    }
}
</script>



<style scoped>
body {
    align-items: center;
}
</style>