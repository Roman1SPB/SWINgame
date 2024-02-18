<template>
    <div id="app">
        <StartingGame @show-table="showTable" />
        <Table v-if="tableVisible" :computer_cards="computer_cards" :player_cards="player_cards" />
    </div>
</template>


<script>

export default {
  data() {
    return {
      computer_cards: [],
      player_cards: [],
      tableVisible: false
    };
  },
  methods: {
    showTable(data) {
      this.computer_cards = data.computer_cards;
      this.player_cards = data.player_cards;
      this.tableVisible = true;
    }
  }
};
</script>
