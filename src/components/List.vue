<template>
  <div class="income-list">
      <IncomeItem v-for="data in state.income" @remove-item="removeItem" :income="data" :key="data.id"/>
  </div>
</template>

<script>
import IncomeItem from './IncomeItem';

export default {
    props: {
        state: Object
    },
    components: {
        IncomeItem
    },
    setup(props, { emit }) {
      function removeItem(id) {
        emit( 'remove-item', id );
      }
      return {
        removeItem
      }
    }
}
</script>

<style scoped>
  .income-list {
    margin-top: 30px;
    padding: 15px;
  }
</style>