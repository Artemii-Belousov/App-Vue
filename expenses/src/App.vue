<template>
  <div id="app">
    <div class="wrapper">
      <header>
        <div class="title">Мои личные расходы</div>
      </header>
      <main>
       
        <AddPaymentForm @addNewPayment="addData" ref="addpaymentForm" />
        <PaymentDisplay 
          v-if="paymentsList.length"
          v-bind:paymentsList="paymentsList" 
          @remove-item="removeItem"
          />
          <p v-else>Список пуст</p>
      </main>
    </div>
  </div>
</template>

<script>



import PaymentDisplay from "./components/paymentDisplay.vue";
import AddPaymentForm from "./components/AddPaymentForm.vue";

export default {
  name: "App",
  components: {
    PaymentDisplay,
    AddPaymentForm,
    
  },
  data() {
    return {
      paymentsList: [
        // {id: 1, date: "28.03.2020", category: "Food", value: 169,},
        // {id: 2, date: "24.03.2020", category: "Transport", value: 360,},
        // {id: 3, date: "24.03.2020", category: "Transport", value: 360,},
      ]
    };
  },
  methods: {
    removeItem(id){
      this.paymentsList = this.paymentsList.filter(i => i.id !==id)
    },
    // addNewPayment(data) {
    //   this.paymentsList = [...this.paymentsList, data];
    // },
    // fetchData() {
    //   return [
    //     {
    //       id: 1,
    //       date: "28.03.2020",
    //       category: "Food",
    //       value: 169,
    //     },
    //     {
    //       id: 2,
    //       date: "24.03.2020",
    //       category: "Transport",
    //       value: 360,
    //     },
    //     {
    //       id: 3,
    //       date: "24.03.2020",
    //       category: "Food",
    //       value: 532,
    //     },
    //   ];
    // },
    addData(data) {
      this.paymentsList.push(data);
    },
  },
  // created() {
  //   this.paymentsList = this.fetchData();
  // },
};
</script>
<style lang='scss' scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.title {
  font-size: 30px;
}
</style>
