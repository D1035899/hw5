<template>
  <h1>物資線上查價平台</h1>
  <h2>品項: 茶裏王台式綠茶 1.25L/瓶</h2>
  <h2>資料範圍: 2021/01/01 ~ 2023/05/07</h2>
  <br>
  <button id="showData">顯示資料</button>
  <button id="closeData" disabled>收起資料</button>
  <table id="table"></table>
  <div id="app">
    <form v-on:submit.prevent="addItem">
      <p>
        ID
        <input type="number" required placeholder="item ID.." v-model="itemID">
      </p>
      <p>
        Amount
        <input type="number" placeholder="Amount of items.." v-model="itemAmount">
      </p>
      <p>
        Price
        <input type="number" placeholder="Price of items.." v-model="itemPrice">
      </p>
      <button type="submit">Add item</button>
    </form>

    <div>
      <p>資料單:</p>
      <ul>
        <li v-for="item in shoppingList">{{ item.id }}, {{ item.amount}},{{item.price}}</li>
      </ul>
    </div>
  </div>

</template>

<script>
export default {
  data() {
    return {
      itemID: null,
      itemAmount: null,
      itemPrice: null,
      shoppingList: [
        { id: 1, amount: 5, price: 25 }
      ]
    }
  },
  methods: {
    addItem(){
      let item = {
        name: this.itemName,
        number: this.itemNumber
      }
      this.shoppingList.push(item)
      this.itemName = null
      this.itemNumber = null
    }
  }
}
</script>

<style scoped>
form {
  border: dashed black 1px;
  width: 200px;
  padding: 20px;
}
</style>