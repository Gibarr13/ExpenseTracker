<template>
    <form @submit.prevent="submitForm">
      <input v-model="name" placeholder="Expense Name" required />
      <input v-model.number="amount" placeholder="Amount" type="number" required />
      <button type="submit">Add Expense</button>
    </form>
  </template>
  
  <script>
  import { ref } from 'vue';
  
  export default {
    setup(props, { emit }) {
      const name = ref('');
      const amount = ref(0);
  
      const submitForm = () => {
        emit('add-expense', { name: name.value, amount: amount.value });
        name.value = '';
        amount.value = 0;
      };
  
      return {
        name,
        amount,
        submitForm,
      };
    },
  };
  </script>
  