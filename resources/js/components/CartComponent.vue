<template>
  <div>
    <h1>Keranjang Belanja</h1>
    <table>
      <thead>
        <tr>
          <th>Name</th>
          <th>Quantity</th>
          <th>Price</th>
          <th></th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(cart, index) in cartdata" :key="index">
          <td>{{ cart.name }}</td>
          <td>{{ cart.stock }}</td>
          <td>{{ cart.price }}</td>
          <td>
            <button-com
              text="Delete"
              @emit-click="delCart(index)"
              color="red"
            />
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  emits: ["emit-del"],
  props: {
    cartdata: {
      type: Array,
      default: () => {
        return [];
      },
    },
  },
  method: {
    delCart(index) {
      this.$emit("emit-del", index);
    },
  },
};
</script>

<style>
</style>