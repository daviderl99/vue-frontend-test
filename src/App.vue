<template>
  <div class="container">
    <button class="button" v-if="!showModal" @click="showModal=true">
      Nupp 1
    </button>
    <ModalItem v-if="showModal" @submit="submitValues" @close="showModal=false" :show="showModal" />
  </div>
</template>

<style lang="scss">
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
.button {
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
</style>

<script lang="ts">
import ModalItem from './components/ModalItem.vue';

export default {
  name: 'App',
  components: {
    ModalItem,
  },
  data() {
    return {
      showModal: false,
    };
  },
  methods: {
    submitValues(values: { valueA: any; valueB: any; }) {
      console.log('A:', values.valueA);
      console.log('B:', values.valueB);
    },
  },
};
</script>
