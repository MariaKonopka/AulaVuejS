<template>
  <div id="app">
    <PlayerForm @player-added="addPlayer" />
    <EmptyMessage :players="players" />
    <PlayerList :players="players" @delete-player="deletePlayer" />
  </div>
</template>

<script>
import PlayerForm from './components/PlayerForm.vue';
import PlayerList from './components/PlayerList.vue';
import EmptyMessage from './components/EmptyMessage.vue';

export default {
  components: {
    PlayerForm,
    PlayerList,
    EmptyMessage
  },
  data() {
    return {
      players: []
    };
  },
  methods: {
    addPlayer(player) {
      this.players.push(player);
    },
    deletePlayer(index) {
      this.players.splice(index, 1);
    }
  }
};
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  max-width: 400px;
  margin: 0 auto;
  text-align: center;
  color: #333;
}
</style>
