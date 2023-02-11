<template>
  <div class="modal" v-if="show">
    <h1>Modaal</h1>
    <div class="inputs">
      <input type="text" v-model="valueA" placeholder="A">
      <input type="text" v-model="valueB" placeholder="B">
    </div>
    <div class="buttons">
      <button @click="submitValues">Sisesta</button>
      <button @click="closeModal">Sulge</button>
    </div>
  </div>
</template>

<style lang="scss">
.modal {
  color: white;
  padding: 20px;
  border: 1px solid var(--color-border);
  border-radius: 5px;
}
.inputs {
  display: flex;
  flex-direction: column;
  margin-bottom: 10px;

  & > input {
    background-color: inherit;
    color: white;
    margin: 5px 0;
    padding: 10px;
    border: 1px solid var(--color-border);
    border-radius: 5px;
  }
}
.buttons {
  display: flex;
  justify-content: space-between;

  & > button {
    background-color: inherit;
    color: white;
    padding: 10px 20px;
    border: 1px solid var(--color-border);
    border-radius: 5px;
    font-size: 16px;
    cursor: pointer;

    &:hover {
      background-color: var(--vt-c-black-mute);
    }
  }
}
</style>

<script lang="ts">
export default {
  name: 'ModalItem',
  props: {
    show: Boolean,
  },
  data() {
    return {
      valueA: '',
      valueB: '',
    };
  },
  methods: {
    submitValues() {
      this.$emit('submit', { valueA: this.valueA, valueB: this.valueB });
      this.closeModal();
    },
    closeModal() {
      this.$emit('close');
    },
  },
};
</script>
