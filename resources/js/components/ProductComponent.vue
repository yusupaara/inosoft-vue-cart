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
                    <th></th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(item, index) in listdata" :key="index">
                    <th>{{item.name}}</th>
                    <td>{{item.desc}}</td>
                    <td>{{item.stock}}</td>
                    <td>{{item.price}}</td>
                    <td><button-com text="Add to cart" @click="addCart(index)" color="blue" /></td>
                </tr>
            </tbody>
        </table>

    </div>
  
</template>

<script>
export default {
  emits:["emit-add"],
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
        this.$emit("emit-add", index)
    }
  }

}
</script>

<style>

</style>