<template>
  <div class="list">
    <table>
      <tr>
        <td class="td">#</td>
        <td class="td">Дата</td>
        <td class="td">Категория</td>
        <td class="td">Сумма</td>
      </tr>
      
      <PaymentItem 
        v-for="(item, i) in paymentsList"
        v-bind:item="item" :key="i"
        v-bind:index="i"
        v-on:remove-item="removeItem"
      />
    </table>
    
      
  </div>
</template>

<script>
import PaymentItem from './PymentItem.vue'
export default {
  name: "PaymentsDisplay",
  components: {
    PaymentItem,
  },
  props: {
    paymentsList: {
      type: Array,
      default: () => [],
    },
  },
  methods:{
    removeItem(id){
      this.$emit('remove-item',id)
    }
  }
};
</script>

<style lang="scss" scoped>
.td {
  font-weight: 600;
}
td {
  width: 100px;
  border: 1px solid red;
  margin-bottom: 5px;
}
</style>
