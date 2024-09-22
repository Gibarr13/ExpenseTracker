<template>
    <div>
      <h2>Expenses</h2>
      <ul>
        <ExpenseItem v-for="expense in expenses" :key="expense.name" :expense="expense" />
      </ul>
    </div>
  </template>
  
  <script>
  import ExpenseItem from './ExpenseItem.vue';
  
  export default {
    props: {
      expenses: Array,
    },
    components: {
      ExpenseItem,
    },
  };
  </script>
  