<template>
  <ul class="player-list" v-if="players.length > 0">
    <li v-for="(player, index) in players" :key="index">
      <div class="player-info">
        <span class="player-name">{{ player.name }}</span>
        <span class="player-age">{{ player.age }} anos</span>
        <span class="player-position">{{ player.position }}</span>
      </div>
      <button @click="deletePlayer(index)">Excluir</button>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    players: {
      type: Array,
      required: true
    }
  },
  methods: {
    deletePlayer(index) {
      this.$emit('delete-player', index);
    }
  }
};
</script>

<style scoped>
.player-list {
  margin-top: 20px;
  padding: 0;
  list-style-type: none;
  max-width: 600px;
  margin: 0 auto;
}

.player-list li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  margin-bottom: 15px;
  border-radius: 12px;
  background-color: #2c2c34;
  box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.25);
  transition: transform 0.2s ease-in-out, background-color 0.3s ease;
  color: #f1f1f1;
}

.player-list li:hover {
  transform: translateY(-5px);
  background-color: #3a3a42;
}

.player-info {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  flex: 1;
}

.player-name {
  font-weight: 600;
  font-size: 20px;
  color: #00d4ff;
}

.player-age,
.player-position {
  font-size: 15px;
  color: #b0b0b5;
}

button {
  background-color: #ff5c5c;
  color: white;
  padding: 10px 16px;
  font-size: 15px;
  font-weight: bold;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 0.3s ease, transform 0.2s;
  margin-left: 15px;
}

button:hover {
  background-color: #ff4242;
  transform: translateY(-3px);
}

button:active {
  background-color: #e04545;
  transform: translateY(0);
}
</style>
