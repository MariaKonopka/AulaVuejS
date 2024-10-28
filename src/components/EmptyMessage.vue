<template>
  <div class="message" v-if="players.length === 0">
    Nenhum jogador cadastrado.
  </div>
</template>

<script>
export default {
  props: {
    players: {
      type: Array,
      required: true
    }
  }
};
</script>

<style scoped>
.message {
  text-align: center;
  font-style: italic;
  margin-top: 30px;
  padding: 20px;
  background-color: #f5f5f5;
  border: 1px dashed #ccc;
  border-radius: 8px;
  color: #555;
  font-size: 16px;
  max-width: 500px;
  margin-left: auto;
  margin-right: auto;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
}
</style>
