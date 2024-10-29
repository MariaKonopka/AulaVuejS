<template>
  <form @submit.prevent="addPlayer">
    <h2>Cadastro de Jogadores</h2>

    <div class="input-group">
      <label for="name">Nome:</label>
      <input type="text" id="name" v-model="newPlayer.name" required />
    </div>

    <div class="input-group">
      <label for="age">Idade:</label>
      <input type="number" id="age" v-model="newPlayer.age" min="1" max="100" required />
    </div>

    <div class="input-group">
      <label for="position">Posição:</label>
      <input type="text" id="position" v-model="newPlayer.position" required />
    </div>

    <button type="submit">Cadastrar Jogador</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      newPlayer: {
        name: '',
        age: '',
        position: ''
      }
    };
  },
  methods: {
    addPlayer() {
      if (this.newPlayer.name && this.newPlayer.age && this.newPlayer.position) {
        this.$emit('player-added', { ...this.newPlayer });
        this.newPlayer = { name: '', age: '', position: '' }; 
      } else {
        alert('Por favor, preencha todos os campos.');
      }
    }
  }
};
</script>

<style scoped>
form {
  max-width: 500px;
  margin: 0 auto;
  padding: 40px;
  background-color: #1c1c1e;
  border-radius: 12px;
  box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.3);
  color: #fff;
  font-family: Arial, sans-serif;
}

h2 {
  text-align: center;
  font-size: 26px;
  margin-bottom: 25px;
  color: #eaeaea;
  text-transform: uppercase;
  letter-spacing: 1.5px;
}

.input-group {
  margin-bottom: 20px;
}

label {
  display: block;
  font-weight: 600;
  margin-bottom: 8px;
  font-size: 14px;
  color: #e0e0e0;
  letter-spacing: 1px;
}

input {
  width: 100%;
  padding: 12px;
  font-size: 16px;
  border: 1px solid #444;
  border-radius: 8px;
  background-color: #333;
  color: #eaeaea;
  transition: border-color 0.3s ease-in-out;
  outline: none;
}

input:focus {
  border-color: #00b4d8;
}

button {
  width: 100%;
  background-color: #00b4d8;
  color: #fff;
  padding: 15px;
  font-size: 18px;
  font-weight: bold;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 0.3s ease-in-out, transform 0.2s;
  letter-spacing: 1px;
  text-transform: uppercase;
}

button:hover {
  background-color: #0096c7;
  transform: translateY(-3px);
}

button:active {
  background-color: #0077b6;
  transform: translateY(0);
}
</style>
