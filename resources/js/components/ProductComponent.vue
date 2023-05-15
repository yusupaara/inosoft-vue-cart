<template>
    <div>
        <h1>Product List</h1>
        <table>
            <thead>
                <tr>
                    <th>Name</th>
                    <th>Description</th>
                    <th>Stock</th>
                    <th>Price</th>
                    <th>Quantity</th>
                    <th></th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(item, index) in listdata" :key="index">
                    <td>{{item.name}}</td>
                    <td>{{item.desc}}</td>
                    <td>{{item.stock}}</td>
                    <td><button type="button" @onClick="functionTest">{{item.price}}</button></td>
                    <td></td>
                    <td><button-com text="Add to cart" @emit-click="addCart(index)" color="blue" /></td>
                </tr>
            </tbody>
        </table>

    </div>
  
</template>

<script>
export default {
  emits:["emit-add","emit-test"],
  props:{
    listdata:{
        type:Array,
        default: () => {
            return[]
        }
    }
  },
  method:{
    addCart(index){
        this.$emit("emit-add", index);
    },
    functionTest() {
        this.$emit("emit-test");
    }
  }
}
</script>

<style>

</style>